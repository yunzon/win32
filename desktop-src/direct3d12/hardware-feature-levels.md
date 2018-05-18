---
title: Hardware Feature Levels
description: Describes the functionality of the 11\_0 through 12\_1 hardware feature levels.
ms.assetid: 'B8304E29-A532-464E-8FAF-075228D8FB73'
keywords: ["DX feature level", "DirectX feature level", "feature level, DX", "feature level, DirectX"]
---

# Hardware Feature Levels

Describes the functionality of the 11\_0 through 12\_1 hardware feature levels.

-   [Numbering Systems](#numbering-systems)
-   [Feature Level Support](#feature-level-support)
-   [Hardware support for DXGI Formats](#hardware-support-for-dxgi-formats)
-   [Related topics](#related-topics)

To handle the diversity of video cards in new and existing machines, Microsoft Direct3D 11 introduced the concept of feature levels. Each video card implements a certain level of Microsoft DirectX (DX) functionality depending on the graphics processing units (GPUs) installed. A feature level is a well defined set of GPU functionality. For instance, the 11\_0 feature level implements the functionality that was implemented in Direct3D 11.

Now when you create a device, you can attempt to create a device for the feature level that you want to request. If the device creation works, that feature level exists, if not, the hardware does not support that feature level. You can either try to recreate a device at a lower feature level or you can choose to exit the application.

The basic properties of feature levels are:

-   All Direct3D 12 drivers will be Feature Level 11.0 or better.
-   A GPU that allows a device to be created meets or exceeds the functionality of that feature level.
-   A feature level always includes the functionality of previous or lower feature levels.
-   A feature level does not imply performance, only functionality. Performance is dependent on hardware implementation.
-   A feature level is chosen when you call [**D3D12CreateDevice**](d3d12createdevice.md).
-   For more detailed information on supported features (especially those marked *Optional* in the table below, which means that the hardware might support the feature but is not required to) call [**CheckFeatureSupport**](id3d12device-checkfeaturesupport.md).

For information about limitations creating non-hardware type devices on certain feature levels, see [Limitations Creating WARP and Reference Devices](https://msdn.microsoft.com/library/windows/desktop/ff728764). For more information on the introduction of feature levels, refer to the Direct3D 11 documentation on [Direct3D feature levels](https://msdn.microsoft.com/library/windows/desktop/ff476876).

## Numbering Systems

Hardware feature levels are *not* the same as API versions. For example, there is a D3D11.3 API, but there is no 11\_3 hardware feature level. Feature levels are defined in the [**D3D\_FEATURE\_LEVEL**](https://msdn.microsoft.com/library/windows/desktop/ff476329) enum.

There are three distinct numbering systems:

-   Direct3D versions use a period; for example, Direct3D 12.0.
-   Shader models use a period; for example, shader model 5.1.
-   Feature levels use an underscore; for example, feature level 12\_0.

## Feature Level Support

The following features are available for each Direct3D feature level.

The headings across the top row are Direct3D feature levels. The headings in the left-hand column are features.



| Feature \\ Feature Level                                                                                                 | 12\_1⁰                    | 12\_0⁰                    | 11\_1¹                   | 11\_0                    |
|--------------------------------------------------------------------------------------------------------------------------|---------------------------|---------------------------|--------------------------|--------------------------|
| Shader Model                                                                                                             | 5.1                       | 5.1                       | 5.1²                     | 5.1²                     |
| [Resource Binding Tier](hardware-support.md)                                                                            | Tier2³                    | Tier2³                    | Tier1³                   | Tier1³                   |
| [Tiled Resources](d3d12-tiled-resources-tier.md)                                                                        | Tier2³                    | Tier2³                    | Optional                 | Optional                 |
| [Conservative Rasterization](conservative-rasterization.md)                                                             | Tier1³                    | Optional                  | Optional                 | No                       |
| [Rasterizer Ordered Views](rasterizer-order-views.md)                                                                   | Yes                       | Optional                  | Optional                 | No                       |
| [Min/Max Filters](d3d12-filter.md)                                                                                      | Yes                       | Yes                       | Optional                 | No                       |
| Map Default Buffer                                                                                                       | Optional                  | Optional                  | Optional                 | Optional                 |
| [Shader Specified Stencil Reference Value](shader-specified-stencil-reference-value.md)                                 | Optional                  | Optional                  | Optional                 | No                       |
| [Typed Unordered Access View Loads](typed-unordered-access-view-loads.md)                                               | 18 formats, more optional | 18 formats, more optional | 3 formats, more optional | 3 formats, more optional |
| [Geometry Shader](https://msdn.microsoft.com/library/windows/desktop/bb205146#geometry-shader-stage) | Yes                       | Yes                       | Yes                      | Yes                      |
| [Stream Out](https://msdn.microsoft.com/library/windows/desktop/bb205121)                                            | Yes                       | Yes                       | Yes                      | Yes                      |
| [DirectCompute / Compute Shader](https://msdn.microsoft.com/library/windows/desktop/ff476331)                                  | Yes                       | Yes                       | Yes                      | Yes                      |
| [Hull and Domain Shaders](https://msdn.microsoft.com/library/windows/desktop/ff476340)                                           | Yes                       | Yes                       | Yes                      | Yes                      |
| [Texture Resource Arrays](https://msdn.microsoft.com/library/windows/desktop/ff476906)                                     | Yes                       | Yes                       | Yes                      | Yes                      |
| [Cubemap Resource Arrays](https://msdn.microsoft.com/library/windows/desktop/ff476906)                                     | Yes                       | Yes                       | Yes                      | Yes                      |
| [BC1 to BC7 Compression](https://msdn.microsoft.com/library/windows/desktop/bb694531)                        | Yes                       | Yes                       | Yes                      | Yes                      |
| [Alpha-to-coverage](https://msdn.microsoft.com/library/windows/desktop/bb205072#alpha-to-coverage)         | Yes                       | Yes                       | Yes                      | Yes                      |
| [Logic Operations (Output Merger)](https://msdn.microsoft.com/library/windows/desktop/hh404457)                                          | Yes                       | Yes                       | Yes                      | Optional                 |
| Target-independent rasterization                                                                                         | Yes                       | Yes                       | Yes                      | No                       |
| [Multiple render target(MRT) with ForcedSampleCount 1](https://msdn.microsoft.com/library/windows/desktop/hh404457)                      | Yes                       | Yes                       | Yes                      | Optional                 |
| [Max forced sample count for UAV-only rendering](https://msdn.microsoft.com/library/windows/desktop/hh404457)                            | 16                        | 16                        | 16                       | 8                        |
| Max Texture Dimension                                                                                                    | 16384                     | 16384                     | 16384                    | 16384                    |
| Max Cubemap Dimension                                                                                                    | 16384                     | 16384                     | 16384                    | 16384                    |
| Max Volume Extent                                                                                                        | 2048                      | 2048                      | 2048                     | 2048                     |
| Max Texture Repeat                                                                                                       | 16384                     | 16384                     | 16384                    | 16384                    |
| Max Anisotropy                                                                                                           | 16                        | 16                        | 16                       | 16                       |
| Max Primitive Count                                                                                                      | 2^32 – 1                  | 2^32 – 1                  | 2^32 – 1                 | 2^32 – 1                 |
| Max Vertex Index                                                                                                         | 2^32 – 1                  | 2^32 – 1                  | 2^32 – 1                 | 2^32 – 1                 |
| Max Input Slots                                                                                                          | 32                        | 32                        | 32                       | 32                       |
| Simultaneous Render Targets                                                                                              | 8                         | 8                         | 8                        | 8                        |
| Occlusion Queries                                                                                                        | Yes                       | Yes                       | Yes                      | Yes                      |
| Separate Alpha Blend                                                                                                     | Yes                       | Yes                       | Yes                      | Yes                      |
| Mirror Once                                                                                                              | Yes                       | Yes                       | Yes                      | Yes                      |
| Overlapping Vertex Elements                                                                                              | Yes                       | Yes                       | Yes                      | Yes                      |
| Independent Write Masks                                                                                                  | Yes                       | Yes                       | Yes                      | Yes                      |
| Instancing                                                                                                               | Yes                       | Yes                       | Yes                      | Yes                      |



 

-   ⁰ Requires the Direct3D 11.3 or Direct3D 12 runtime.
-   ¹ Requires the Direct3D 11.1 runtime.
-   ² Shader model 5.0 can optionally support double-precision shaders, extended double-precision shaders, the **SAD4** shader instruction, and partial-precision shaders. To determine the shader model 5.0 options that are available, call [**ID3D12Device::CheckFeatureSupport**](id3d12device-checkfeaturesupport.md). Some compatibility depends on what hardware you are running on: Shader model 5.1 is only supported on hardware that supports the DirectX 12 API, regardless of the feature level that's being used. DirectX 11 hardware only supports up to shader model 5.0. The DirectX 12 API only goes down to feature level 11\_0.
-   ³ Higher tiers are optional.
-   Feature levels 12.0 and 12.1 require the Direct3D 11.3 or Direct3D 12 runtime.
-   Feature level 11.1 requires the Direct3D 11.1 runtime.
-   Feature level 11.0 requires the Direct3D 11.0 runtime.

## Hardware support for DXGI Formats

To view tables of DXGI formats and hardware features, refer to:

-   [DXGI Format Support for Direct3D Feature Level 12.1 Hardware](https://msdn.microsoft.com/library/windows/desktop/mt426648)
-   [DXGI Format Support for Direct3D Feature Level 12.0 Hardware](https://msdn.microsoft.com/library/windows/desktop/mt426647)
-   [DXGI Format Support for Direct3D Feature Level 11.1 Hardware](https://msdn.microsoft.com/library/windows/desktop/mt427456)
-   [DXGI Format Support for Direct3D Feature Level 11.0 Hardware](https://msdn.microsoft.com/library/windows/desktop/mt427455)
-   [Hardware Support for Direct3D 10Level9 Formats](https://msdn.microsoft.com/library/windows/desktop/ff471324)
-   [Hardware Support for Direct3D 10.1 Formats](https://msdn.microsoft.com/library/windows/desktop/cc627091)
-   [Hardware Support for Direct3D 10 Formats](https://msdn.microsoft.com/library/windows/desktop/cc627090)

## Related topics

<dl> <dt>

[Capability Querying](capability-querying.md)
</dt> <dt>

[Understanding Direct3D 12](directx-12-getting-started.md)
</dt> </dl>

 

 



