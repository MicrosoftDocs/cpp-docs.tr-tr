---
description: 'Daha fazla bilgi edinin: genel sınıf tasarımı Felseno'
title: Genel Sınıf Tasarımı Felsefesi
ms.date: 11/04/2016
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: 96069b5f30cbca8bb310de6b917fd65a280700b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193467"
---
# <a name="general-class-design-philosophy"></a>Genel Sınıf Tasarımı Felsefesi

Microsoft Windows, C++ dili popüler hale gelmeden önce uzun süredir tasarlandı. Binlerce uygulama C-dil Windows uygulama programlama arabirimini (API) kullandığından, bu arabirim, daha sonra öngörülebilir bir şekilde tutulacaktır. Bu nedenle, herhangi bir C++ Windows arabiriminin, yordamsal C-dil API 'sinin üzerine oluşturulması gerekir. Bu, C++ uygulamalarının C uygulamalarıyla birlikte bir arada bulunabilebilmesini güvence altına alır.

Microsoft Foundation Class Kitaplığı, Windows için aşağıdaki tasarım hedeflerini karşılayan nesne yönelimli bir arabirimdir:

- Windows için bir uygulama yazma çabasında önemli bir azalma.

- C dili API 'siyle benzer yürütme hızı.

- Minimum kod boyutu ek yükü.

- Herhangi bir Windows C işlevini doğrudan çağırma özelliği.

- Mevcut C uygulamalarının C++ ' ya daha kolay dönüştürülmesi.

- C dili Windows programlama deneyiminin var olan temel öğesinden faydalanabilir.

- C++ ile C ile kıyasla Windows API 'sinin daha kolay kullanımı.

- ActiveX denetimleri, veritabanı desteği, yazdırma, araç çubukları ve durum çubukları gibi karmaşık özellikler, daha kolay soyutlamadır.

- C++ dil özelliklerini etkin bir şekilde kullanan C++ için doğru Windows API 'SI.

MFC kitaplığının tasarımı hakkında daha fazla bilgi için bkz.:

- [Uygulama çerçevesi](application-framework.md)

- [C dili API 'siyle ilişki](relationship-to-the-c-language-api.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
