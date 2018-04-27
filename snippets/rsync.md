### Get files

	rsync -e ssh -avz \
		root@proj.lxc:/var/www/html/proj/web/typo3conf/ext/ \
		/home/nifor/Documents/proj/prod/ext/

### Get files from files list

	rsync -e ssh -arzmv \
		--files-from=/home/nifor/Documents/proj/source_file_list.txt \
		root@proj.lxc:/var/www/html/proj/web \
		/home/nifor/Documents/proj/prod2
