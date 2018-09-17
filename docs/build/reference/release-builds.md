---
title: Yayın derlemeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8d4f0d9b1bf0401cc6630b61449e87d72ff675
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722130"
---
# <a name="release-builds"></a>Yayın Derlemeleri

Yayın derlemesi iyileştirmeleri kullanır. Yayın derlemesi oluşturma için en iyi duruma getirme kullandığınızda, derleyici sembolik hata ayıklama bilgisi üretmez. Kod için izleme ve onay oluşturulmaz olgu birlikte sembolik hata ayıklama bilgilerini olmaması çağırır, yürütülebilir dosyanızın boyutunu azaltılır ve bu nedenle daha hızlı olduğu anlamına gelir.

Bu bölümde, neden ve ne zaman bir yayın yapısı için hata ayıklama derlemeden değiştirmek istiyorsunuz bilgi sunar. Ayrıca bazı hata ayıklama'dan bir yayın yapısı için değiştirilirken karşılaşabileceğiniz sorunlar açıklanır:

- [Yayın derlemesi oluşturma](../../build/reference/how-to-create-a-release-build.md)

- [Yayın Derlemesi Oluşturmadaki Genel Sorunlar](../../build/reference/common-problems-when-creating-a-release-build.md)

- [Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)

   - [ASSERT deyimleri İnceleme](../../build/reference/using-verify-instead-of-assert.md)

   - [Belleğin üzerine yazma için onay hata ayıklama derlemesini kullanma](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)

   - [Yayın derlemesinde hata ayıklama](../../build/reference/how-to-debug-a-release-build.md)

   - [Bellek Üzerine Yazmalarını Denetleme](../../build/reference/checking-for-memory-overwrites.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio'da C++ Projeleri Derleme](../../ide/building-cpp-projects-in-visual-studio.md)<br/>
[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)