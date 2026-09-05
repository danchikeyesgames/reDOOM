## WAD Subsystem


#### BIG-endian vs little-endian

Number: 0x12345678

Bytes order type     addr0  addr1  addr2  addr3
Big-endian (ARM)       12     34     56     78
Little-endian (x86)    78     56     34     12

**Doom WAD files use LE notation**

#### WAD file structure


```
+----------------------------------------+  <--+
|                  id                    |     |
|               numlumps                 |    header
|         lumpinfo table offset          |     |
+----------------------------------------+  <--+
|                                        |
|                                        |
|                                        |
|                                        |
|                                        |
|                LUMPS                   |
|                                        |
|                                        |
|                                        |
|                                        |
|                                        |
|                                        |
|                                        |
|                                        |
|----------------------------------------|  <--+   <-- start lumpinfo table
|                 filepos                |     |
|                  size                  |   lumpinfo
|                  name                  |     |
|                                        |     |
|----------------------------------------|  <--+
|                                        |
|                  ...                   |
|                                        |
+----------------------------------------+


^                                        ^
|                4 bytes                 |
+----------------------------------------+

```

#### Lump classify

"PNAMES":
{
    int numpatches;
    char patchname1[8];
    char patchname2[8];
    ...
}

"TEXTURE1"
"TEXTURE2"  -- map textures, 1) for shareware 2) for comercial

{
    int numtextures;
    int directory1;    <--- maptexture offset
    int derictory2;
    ...
    maptexture_t texture1;
    maptexture_t texture2;
    ...
    {
        char name[8]
        boolean	masked;
        short width;
        short height;
        int padding;
        short patchcount;
        mappatch_t	patches[1];   <--- describe rectangular texture
    }
}

"S_START"
"S_END"      <----- Sprites location


"F_START"
"F_END"      <----- Flats location


"COLORMAP"