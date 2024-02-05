
cd /usr/local/bin

vi xsync

chmod + xsync

脚本内容

	#!/bin/bash
	
	if [ $# -lt 1 ]
	then
	    echo Not Enough Arguement!
	    exit;
	fi
	
	for file in $@
	do
		if [ -e $file ]
		then
			pdir=$(cd -P $(dirname $file); pwd)
			fname=$(basename $file)
				
	
			for host in kc001 kc002 kc003
			do
				ssh $host "mkdir -p $pdir"
				rsync -av $pdir/$fname $host:$pdir
			done
		fi
	
	done
