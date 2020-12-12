---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1256'
title: Bağlayıcı Araçları Hatası LNK1256
ms.date: 11/04/2016
f1_keywords:
- LNK1256
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
ms.openlocfilehash: 33dc240e194d93253f3bbf3a5fcd56722b6634d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193806"
---
# <a name="linker-tools-error-lnk1256"></a>Bağlayıcı Araçları Hatası LNK1256

ALıNK işlemi başarısız oldu: neden

LNK1256 için genel bir neden, derleme için yanlış sürüm numarasıdır. Derleme sürüm numarasının herhangi bir bölümü için 65535 değerine izin verilmez. Derleme sürümleri için geçerli Aralık 0-65534 ' dir.

LNK1256, Ayrıca, ALINK adlandırılmış anahtar kapsayıcısını bulamamışsa de oluşabilir. Anahtar kapsayıcısını silin ve [Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool)kullanarak tanımlayıcı ad CSP 'ye yeniden ekleyin.

LNK1256 için başka bir nedenden dolayı bağlayıcı ve Alink.dll arasında bir sürüm uyumsuzluğu vardır. Bunun nedeni, bozuk bir Visual Studio yüklemesi olabilir. Visual Studio 'Yu onarmak veya yeniden yüklemek için Windows Denetim Masası 'ndaki **Programlar ve Özellikler ' i** kullanın.

Aşağıdaki örnek LNK1256 oluşturur:

```cpp
// LNK1256.cpp
// compile with: /clr /LD
// LNK1256 expected
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];
public class CMyClass {
public:
   int value;
};
```
