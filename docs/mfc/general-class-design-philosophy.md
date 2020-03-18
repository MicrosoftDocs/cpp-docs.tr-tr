---
title: Genel Sınıf Tasarımı Felsefesi
ms.date: 11/04/2016
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: 34a173802e3fa43615c05da4ce747592f851228f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441194"
---
# <a name="general-class-design-philosophy"></a>Genel Sınıf Tasarımı Felsefesi

Microsoft Windows, C++ dilin popüler hale gelmeden önce uzun süredir tasarlandı. Binlerce uygulama C-dil Windows uygulama programlama arabirimini (API) kullandığından, bu arabirim, daha sonra öngörülebilir bir şekilde tutulacaktır. Bu C++ nedenle, herhangi bir Windows arabiriminin, yordamsal C dili API 'sinin üzerine oluşturulması gerekir. Bu, uygulamaların C++ C uygulamalarıyla birlikte bir arada bulunabilebilmesini güvence altına alır.

Microsoft Foundation Class Kitaplığı, Windows için aşağıdaki tasarım hedeflerini karşılayan nesne yönelimli bir arabirimdir:

- Windows için bir uygulama yazma çabasında önemli bir azalma.

- C dili API 'siyle benzer yürütme hızı.

- Minimum kod boyutu ek yükü.

- Herhangi bir Windows C işlevini doğrudan çağırma özelliği.

- Var olan C uygulamalarının ' ye C++daha kolay dönüştürülmesi.

- C dili Windows programlama deneyiminin var olan temel öğesinden faydalanabilir.

- C ile C++ sürümünden daha kolay Windows API kullanımı.

- ActiveX denetimleri, veritabanı desteği, yazdırma, araç çubukları ve durum çubukları gibi karmaşık özellikler, daha kolay soyutlamadır.

- Etkin olarak dil özelliklerini C++ kullanan C++ doğru Windows API 'si.

MFC kitaplığının tasarımı hakkında daha fazla bilgi için bkz.:

- [Uygulama çerçevesi](../mfc/application-framework.md)

- [C Dili API'sına yönelik ilişki](../mfc/relationship-to-the-c-language-api.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
