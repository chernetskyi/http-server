# :computer: SoftServer :computer:
> minimalistic http-server for static pages

[![forthebadge](https://forthebadge.com/images/badges/made-with-c-plus-plus.svg)](https://forthebadge.com)
[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org) 
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

## Table of contents
 - [Getting started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installing](#installing)
   - [Usage](#usage)
 - [Contributing](#contributing)
 - [Team](#team)
 - [License and Copyright](license-and-copyright)

## Getting started

### Prerequisites
   - Boost 1.69 or newer
   > Boost 1.65 or older is incompatible. Regarding updating Boost on Ubuntu 16/18, look [here](https://www.osetc.com/en/how-to-install-boost-on-ubuntu-16-04-18-04-linux.html). Uninstallation of previous boost-dev packages might be necessary.   
   - CMake 3.10 or newer

### Installing
1. Clone project.
2. Compile project.
     ```bash
     mkdir build && cd build
     cmake -G"Unix Makefiles" ..
     make
     ```
3. Run async specifying at least wanted port and a path for served documents. Run with `--help` to learn more about command line options.
     
     Example: `async -p 8080 /srv/http`
4. Enjoy! :tada:

### Usage 
Simply open the webpage in the browser :globe_with_meridians:

## Contributing
Pull requests :octocat: are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Team
| | |
| :---: | :---: |
| Volodymyr Chernetskyi | Hermann Yavorskyi |
| <img src="https://upload.wikimedia.org/wikipedia/ru/0/01/2003tmntscreenshot.jpg"> | <img src="https://upload.wikimedia.org/wikipedia/ru/a/a7/Red_Donatello.jpg"> |
| [chernetskyi](https://github.com/chernetskyi) | [wardady](https://github.com/wardady) |
| Andrii Koval | Petro Franchuk |
| <img src="https://upload.wikimedia.org/wikipedia/ru/2/23/Red_Raphael.jpg"> | <img src="https://upload.wikimedia.org/wikipedia/ru/f/f9/Red_Michelangelo.jpg"> |
| [andrwkoval](https://github.com/andrwkoval) | [franchukpetro](https://github.com/franchukpetro) |
| Oleg Farenyuk | Yulianna Tymchenko |
| <img src="https://www.ninjaturtles.ru/forum/pic/12843.jpg"> | <img src="https://vignette.wikia.nocookie.net/tmnt-polska/images/2/2d/April-1987.png/revision/latest?cb=20160503145802&path-prefix=pl"> |
| [indrekis](https://github.com/indrekis) | [neverlandjt](https://github.com/neverlandjt) |


See also the list of [contributors](https://github.com/chernetskyi/http-server/contributors) who participated in this project.

## License and Copyright
[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org) 

This project is licensed under the [MIT License](https://choosealicense.com/licenses/mit/).

© 2019 Volodymyr Chernetskyi, Hermann Yavorskyi, Andrii Koval, Petro Franchuk, Yulianna Tymchenko, Oleg Farenyuk
