# Learn data science from kaggle

* Working environment
    + [Docker Kaggle Python](https://github.com/kaggle/docker-python)
    + [How to use the docker image](http://blog.kaggle.com/2016/02/05/how-to-get-started-with-data-science-in-containers/)
    + To make it to work for Mac, I have to adjust the code from the "How to" page and add the following code to my `.bash_profile` file.
    
```bash
kpython(){
  docker run -v $PWD:/tmp/working -w=/tmp/working --rm -it kaggle/python python "$@"
}
ikpython() {
  docker run -v $PWD:/tmp/working -w=/tmp/working --rm -it kaggle/python ipython
}
kjupyter() {
  (sleep 3 && open "http://$(docker-machine ip default):8888")&
  docker run -v $PWD:/tmp/working -w=/tmp/working -p 8888:8888 --rm -it kaggle/python jupyter notebook --allow-root --no-browser --ip="0.0.0.0" --notebook-dir=/tmp/working
}
```

**Change directory to any directory that you want to be your working directory and run `kpython` as a replacement for calling `python`, `ikpython` for `ipython`, and `kjupyter` for `jupyter`.**

* [A Data Science Framework: To Achieve 99% Accuracy
](https://www.kaggle.com/ldfreeman3/a-data-science-framework-to-achieve-99-accuracy)
