---
title: Bağlayıcı Araçları Hatası LNK1256
ms.date: 11/04/2016
f1_keywords:
- LNK1256
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
ms.openlocfilehash: bedf96262944d59737a39a942021cdec9445f3b8
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990948"
---
# <a name="linker-tools-error-lnk1256"></a>Bağlayıcı Araçları Hatası LNK1256

ALıNK işlemi başarısız oldu: neden

LNK1256 için genel bir neden, derleme için yanlış sürüm numarasıdır. Derleme sürüm numarasının herhangi bir bölümü için 65535 değerine izin verilmez. Derleme sürümleri için geçerli Aralık 0-65534 ' dir.

LNK1256, Ayrıca, ALINK adlandırılmış anahtar kapsayıcısını bulamamışsa de oluşabilir. Anahtar kapsayıcısını silin ve [sn. exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool)kullanarak tanımlayıcı ad CSP 'ye yeniden ekleyin.

LNK1256 için başka bir nedenden dolayı bağlayıcı ve ALink. dll arasında sürüm uyuşmazlığı olur. Bunun nedeni, bozuk bir Visual Studio yüklemesi olabilir. Visual Studio 'Yu onarmak veya yeniden yüklemek için Windows Denetim Masası 'ndaki **Programlar ve Özellikler ' i** kullanın.

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
