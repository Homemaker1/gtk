# Note: gdksettings.c gets included from xsettings-client.c, do not add here
gdk_x11_sources = files([
  'gdkapplaunchcontext-x11.c',
  'gdkasync.c',
  'gdkcursor-x11.c',
  'gdkdevice-core-x11.c',
  'gdkdevice-xi2.c',
  'gdkdevicemanager-core-x11.c',
  'gdkdevicemanager-x11.c',
  'gdkdevicemanager-xi2.c',
  'gdkdisplay-x11.c',
  'gdkdnd-x11.c',
  'gdkeventsource.c',
  'gdkeventtranslator.c',
  'gdkgeometry-x11.c',
  'gdkglcontext-x11.c',
  'gdkkeys-x11.c',
  'gdkmain-x11.c',
  'gdkmonitor-x11.c',
  'gdkproperty-x11.c',
  'gdkscreen-x11.c',
  'gdkselection-x11.c',
  'gdkvisual-x11.c',
  'gdkvulkancontext-x11.c',
  'gdkwindow-x11.c',
  'gdkxftdefaults.c',
  'gdkxid.c',
  'xsettings-client.c',
])

gdk_x11_public_headers = files([
  'gdkx-autocleanups.h',
  'gdkx11applaunchcontext.h',
  'gdkx11cursor.h',
  'gdkx11device-core.h',
  'gdkx11device-xi2.h',
  'gdkx11device.h',
  'gdkx11devicemanager-core.h',
  'gdkx11devicemanager-xi2.h',
  'gdkx11devicemanager.h',
  'gdkx11display.h',
  'gdkx11dnd.h',
  'gdkx11glcontext.h',
  'gdkx11keys.h',
  'gdkx11monitor.h',
  'gdkx11property.h',
  'gdkx11screen.h',
  'gdkx11selection.h',
  'gdkx11utils.h',
  'gdkx11visual.h',
  'gdkx11window.h',
])

install_headers(gdk_x11_public_headers, subdir: 'gtk-4.0/gdk/x11/')
install_headers('gdkx.h', subdir: 'gtk-4.0/gdk/')

gdk_x11_deps = [
  xrender_dep,
  xi_dep,
  xext_dep,
  x11_dep,
  xcursor_dep,
  xdamage_dep,
  xfixes_dep,
  xcomposite_dep,
  xrandr_dep,
  xinerama_dep,
]

libgdk_x11 = static_library('gdk-x11',
                            gdk_x11_sources, gdkconfig, gdkenum_h,
                            include_directories: [ confinc, gdkinc, ],
                            c_args: [
                              '-DGDK_COMPILATION',
                              '-DG_LOG_DOMAIN="Gdk"',
                            ] + common_cflags,
                            link_args: common_ldflags,
                            dependencies: [ gdk_deps, gdk_x11_deps, ])
