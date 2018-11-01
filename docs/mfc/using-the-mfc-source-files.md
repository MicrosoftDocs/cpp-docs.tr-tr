---
title: MFC Kaynak Dosyalarını Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
ms.openlocfilehash: 40decb64914167061f6538df36d086347f52e1b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659296"
---
# <a name="using-the-mfc-source-files"></a>MFC Kaynak Dosyalarını Kullanma

Microsoft Foundation Class (MFC) kitaplığı, tam kaynak kodu sağlar. Üstbilgi (.h) \atlmfc\include dizinde dosyalardır; Uygulama dosyaları (.cpp) \atlmfc\src\mfc dizinindedir.

Bu makaleler ailesi her sınıf'ın çeşitli bölümleri, bu açıklamalar ne anlama gelir ve her bölümde bulmak beklemelisiniz yorum yapmak için MFC kullanan kuralları açıklar. Visual C++ sihirbazları, sizin için oluşturdukları sınıflar için benzer kurallar kullanır ve size büyük olasılıkla bu kuralları için kendi kodunuzu kullanışlı.

Alışkın olabileceğiniz **genel**, **korumalı**, ve **özel** C++ anahtar sözcükleri. MFC üstbilgi dosyalarına bakıldığında her sınıf birkaç her birinin sahip olduğunu bulabilirsiniz. Örneğin, genel üye değişkenleri ve işlevleri birden çok altında olması olabilir **genel** anahtar sözcüğü. Üye değişkenleri ve işlevleri izin verilen erişim türü tarafından değil, kullanımda göre MFC ayıran olmasıdır. MFC kullanan **özel** tutumlu; öğeler bile uygulama ayrıntılarını genel olarak korunur ve birden çok kez herkese açık olarak kabul. Uygulama Ayrıntıları erişimi önerilmez olsa da, MFC kararı size bırakır.

MFC kaynak dosyalarını ve MFC Uygulama Sihirbazı oluşturur dosyaları içinde (genellikle bu sırayla) açıklamaları gibi sınıf bildirimi içinde bulabilirsiniz:

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

Bu makale ailesinde ele alınan konular:

- [Açıklamalara bir örnek](../mfc/an-example-of-the-comments.md)

- [/ / Uygulama açıklaması](../mfc/decrement-implementation-comment.md)

- [/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)

- [/ / Öznitelikler açıklaması](../mfc/decrement-attributes-comment.md)

- [/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)

- [/ / Geçersiz kılınabilen öğelerle ilgili açıklama](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)

