---
layout: single
title: ExCL Privilege Levels
permalink: /excl-privilege-levels/
toc: false
---

A unique characteristic of ExCL is our approach to providing increased access to resources to facilitate experimental computer science. Projects and users can request more privileged access to the resources. Given that these higher privileged levels require more restrictions on the hardware resources and typically more effort from our staff, fewer ExCL users will be granted increased levels of privilege access.

## Levels of Access
Our ExCL approach to facilitating experimental computer science on these resources is best summarized with the following figure and table.

Keep in mind that increased levels of privilege will require more support and as such fewer projects and users at these elevated levels can be supported.

![Access Levels]({% link /assets/images/access-levels.png %}){: .align-center}

These levels can be summarized in the follow matrix:

| Level | ExCL Privilege Level | Shared Resource Access | Exclusive Resource Access | Modify Software Stack (not OS or drivers) | Modify OS and/or drivers | Modify hardware configuration via firmware or other tools | Reconfigure hardware |
|-------|----------------------|------------------------|---------------------------|-------------------------------------------|--------------------------|-----------------------------------------------------------|----------------------|
| 1     | Default              | Y                      |                           |                                           |                          |                                                           |                      |
| 2     | Exclusive            | Y                      | Y                         |                                           |                          |                                                           |                      |
| 3     | User Software Stack  | Y                      | Y                         | Y                                         |                          |                                                           |                      |
| 4     | OS                   | Y                      | Y                         | Y                                         | Y                        |                                                           |                      |
| 5     | Firmware             | Y                      | Y                         | Y                                         | Y                        | Y                                                         |                      |
| 6     | Hardware             | Y                      | Y                         | Y                                         | Y                        | Y                                                         | Y                    |