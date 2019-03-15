---
title: Bağlayıcı Araçları Hatası LNK1256
ms.date: 11/04/2016
f1_keywords:
- LNK1256
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
ms.openlocfilehash: 47c20f24a2fe26cc96d5efcf359652a40af508ee
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811543"
---
# <a name="linker-tools-error-lnk1256"></a>Bağlayıcı Araçları Hatası LNK1256

ALINK işlemi başarısız oldu: nedeni

LNK1256 yaygın bir nedeni bir derleme için yanlış sürüm numarasıdır. Herhangi bir bölümü için derleme sürüm numarası 65535 değerine izin verilmiyor. Derleme sürümleri için geçerli aralık 0 - ise 65534.

ALINK adlandırılmış bir anahtar kapsayıcısı bulunamadı, LNK1256 de neden olabilir. Anahtar kapsayıcısını silme ve kullanarak yeniden tanımlayıcı ad CSP eklemek [Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool).

LNK1256 başka bir nedeni bağlayıcı ve Alink.dll arasında sürüm uyuşmazlığı olmasıdır. Bu, bozuk bir Visual Studio yüklemesinin neden olabilir. Kullanım **programlar ve Özellikler** Visual Studio'yu yeniden yükleyin veya onarmak için Windows Denetim Masası'nda.

Aşağıdaki örnek, LNK1256 oluşturur:

```
// LNK1256.cpp
// compile with: /clr /LD
// LNK1256 expected
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];
public class CMyClass {
public:
   int value;
};
```