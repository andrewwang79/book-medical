# VTK

* [VTK基础及应用开发教程](https://blog.csdn.net/www_doling_net/article/details/8763686)
* []()
* [vtk基础](https://www.zhihu.com/column/c_1406939506679951360)

## vtk.js
* https://juejin.cn/post/6854573220121542670

## VTK集成EGL编译
```

git clone https://gitlab.kitware.com/vtk/vtk.git && cd vtk && git checkout v8.2.0
mkdir /app/vtk_install && mkdir build
cd build
// 重点是-DVTK_USE_X=OFF -DVTK_OPENGL_HAS_EGL=ON -DVTK_OPENGL_HAS_OSMESA=OFF
cmake -DCMAKE_INSTALL_PREFIX=/app/vtk_install -DCMAKE_BUILD_TYPE=Release -DBUILD_SHARED_LIBS=ON -DBUILD_EXAMPLES=OFF -DBUILD_TESTING=OFF -DVTK_Group_Views=ON -DModule_vtkRenderingParallel=ON -DVTK_Group_Rendering=ON -DVTK_Group_StandAlone=ON -DVTK_USE_X=OFF -DVTK_OPENGL_HAS_EGL=ON -DVTK_OPENGL_HAS_OSMESA=OFF -DVTK_RENDERING_BACKEND=OpenGL2 -DVTK_DEFAULT_RENDER_WINDOW_OFFSCREEN=ON
make -j8 && make install
```
