project('ImGui_Interpolation', 'cpp',
        version : '1.0.0',
        default_options : ['warning_level=3', 'cpp_std=c++14'])

# Specifying the ImGui source files

imgui_path = 'ThirdParty/imgui'
imgui_inc = include_directories(imgui_path)

imgui_src = files(
    imgui_path / 'imgui.cpp',
    imgui_path / 'imgui_draw.cpp',
    imgui_path / 'imgui_widgets.cpp',
    imgui_path / 'imgui_tables.cpp',
    imgui_path / 'backends/imgui_impl_win32.cpp',
    imgui_path / 'backends/imgui_impl_dx11.cpp'
)

project_deps = [
    meson.get_compiler('cpp').find_library('d3d11'),
    meson.get_compiler('cpp').find_library('d3dcompiler'),
    meson.get_compiler('cpp').find_library('dwmapi')
]

ImGui_Interpolation = executable('ImGui_Interpolation',
                                 sources : [
                                     'src/main.cpp',
                                     imgui_src
                                 ],
                                 include_directories : [imgui_inc],
                                 dependencies : project_deps,
                                 install : true)

test('test', ImGui_Interpolation)