---
title: Genel sınıf tasarımı felsefesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fe64ee4d9e6fc678d97c3e9fe37a85e53807541
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416649"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

