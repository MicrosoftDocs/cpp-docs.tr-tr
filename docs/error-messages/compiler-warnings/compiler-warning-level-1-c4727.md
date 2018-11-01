---
title: Derleyici Uyarısı (düzey 1) C4727
ms.date: 11/04/2016
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: be1a248fc2709706e137b543344966735c19064e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490577"
---
# <a name="compiler-warning-level-1-c4727"></a>Derleyici Uyarısı (düzey 1) C4727

"Obj_file_1 ve obj_file_2 bulunan aynı zaman damgasına sahip pch_file adlı PCH.  İlk PCH kullanılıyor.

Birden çok derleme ile derleme yaparken C4727 gerçekleşir **/Yc**, ve derleyici olduğu aynı .pch zaman damgasına sahip tüm .obj dosyaları işaretlemek kullanabilirsiniz.

Çözmek için bir kaynak dosyasını derlemek **/Yc /c** (pch oluşturur), ve diğerleri ile ayrı olarak derleme **/Yu /c** (pch kullanır), sonra bunları birbirine bağlayın.

Bunu, aşağıdaki olmadı ve C4727 oluşturur:

**cl/CLR /GL a.cpp b.cpp c.cpp /Ycstdafx.h**

Bunun yerine aşağıdakileri:

**cl/CLR /GL a.cpp /Ycstdafx.h /c**

**cl/CLR /GL b.cpp c.cpp /Yustdafx.h/Link a.obj**

Daha fazla bilgi için bkz.

- [/Yc (Önceden Derlenmiş Üst Bilgi Dosyası Oluştur)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (Önceden Derlenmiş Üst Bilgi Dosyasını Kullanma)](../../build/reference/yu-use-precompiled-header-file.md)