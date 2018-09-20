---
title: MFC kullanarak kaynak dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e63383e372227dc14ce90843b03b6cb0c029b52a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383863"
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

