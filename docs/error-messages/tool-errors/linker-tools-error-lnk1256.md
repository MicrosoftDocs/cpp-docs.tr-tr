---
title: Bağlayıcı araçları hatası LNK1256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs:
- C++
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a711343eaf64a9ef1c46a5044cb3d6a2f84c5f7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050651"
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