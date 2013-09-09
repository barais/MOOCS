MOOCS
=====

Script to build web sites from courses

The goal is to build courses website using ffmpeg

`export NAME=TAACours1 ; wget http://github.com/barais/MOOCS/raw/master/cours.tgz -P /tmp ; mkdir -p /tmp/$NAME ; tar -C "/tmp/$NAME" -xzf /tmp/cours.tgz && sed -i "s/PROJECTTITLE/${NAME}/g" /tmp/"$NAME"/index.html ; xfce4-terminal --tab -x ffmpeg -y -f video4linux2 -r 15 -s 800x600 -i /dev/video1 -vcodec vp8 /tmp/$NAME/assets/cam.webm && xfce4-terminal --tab -x ffmpeg -y -f alsa -ac 2 -i pulse -f x11grab -qscale 2 -r 10 -s ``xdpyinfo | grep dimensions | awk '{print $2}' | awk -Fx '{print $1"x"$2}'`` -i :0.0 -s 1024x768 -acodec libvorbis -vcodec vp8 -preset ultrafast -threads 0 -crf 22 /tmp/$NAME/assets/screen.webm`



