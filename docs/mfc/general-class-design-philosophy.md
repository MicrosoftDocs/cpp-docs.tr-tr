---
title: Genel Sınıf Tasarımı Felsefesi
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: 4dfa11c73703f5f2d3d17f8278610d32178af679
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219625"
---
# <a name="general-class-design-philosophy"></a>Genel Sınıf Tasarımı Felsefesi

C++ dili popüler olmadan uzun süre önce Microsoft Windows tasarlanmıştır. Uygulamaların binlerce C dili Windows uygulama programlama arabirimi (API) kullandığından, bu arabirim yakın bir gelecekte korunur. Herhangi bir C++ Windows arabirimi, bu nedenle yordam C dili API temelinde oluşturulmalıdır. Bu, C++ uygulamalarının C uygulamaları ile bir arada mümkün olacağını garanti eder.

Microsoft Foundation Class Kitaplığı, nesne yönelimli bir arabirim için aşağıdaki tasarım hedefleri karşılayan bir Windows verilmiştir:

- Windows için uygulama yazmak için gereken çabayı önemli ölçüde azalma.

- Yürütme hızını C dili API için karşılaştırılabilir.

- En düşük kod boyutu yükü.

- Doğrudan herhangi bir Windows C işlevini çağırmak için yeteneği.

- C++ var olan C uygulamalarda daha kolay dönüştürme.

- C dili Windows programlama deneyimi mevcut temelden yararlanma olanağı.

- Windows API c++ c ile daha kolay kullanımı

- ActiveX denetimleri, veritabanı desteği, yazdırma, araç çubuklarını ve durum çubukları gibi özellikleri daha kolay kullanımı henüz güçlü özetlerini karmaşık.

- C++ dili uygulama özellikleri etkili bir şekilde kullanan C++ için Windows API true.

MFC Kitaplığı'nın tasarımı hakkında daha fazla bilgi için bkz:

- [Uygulama Çerçevesi](../mfc/application-framework.md)

- [C Dili API'sına yönelik ilişki](../mfc/relationship-to-the-c-language-api.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
