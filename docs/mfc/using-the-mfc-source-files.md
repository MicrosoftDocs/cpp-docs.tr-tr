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
ms.openlocfilehash: 6f23f792f750e4352494bf3e4bde08f0fe360439
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980483"
---
# <a name="using-the-mfc-source-files"></a>MFC Kaynak Dosyalarını Kullanma

Microsoft Foundation Class (MFC) kitaplığı tam kaynak kodu sağlar. Üst bilgi dosyaları (. h), \atlmfc\include dizininde bulunur; uygulama dosyaları (. cpp), \atlmfc\src\mfc dizininde bulunur.

Bu makale ailesinde, MFC 'nin her bir sınıfın çeşitli parçalarını, bu açıklamaların ne anlama geldiğini ve her bölümde bulmayı beklemeniz gerekenleri açıklama eklemek için kullandığı kurallar açıklanmaktadır. Görsel C++ sihirbazlar, sizin için oluşturdukları sınıflar için benzer kuralları kullanır ve muhtemelen bu kuralları kendi kodunuz için yararlı bulacaktır.

**Ortak**, **korumalı**ve **özel** C++ anahtar sözcükler hakkında bilgi sahibi olabilirsiniz. MFC başlık dosyalarında her bir sınıfın birkaç tane olabilir. Örneğin, ortak üye değişkenleri ve işlevleri birden fazla **ortak** anahtar sözcük altında olabilir. Bunun nedeni, MFC 'nin üye değişkenlerini ve işlevleri, izin verilen erişim türüne göre değil, kullanımına göre ayırır. MFC **özel** olarak gelişigüzel kullanır. Uygulama ayrıntıları olarak kabul edilen öğeler genellikle **korunur**ve birçok kez **geneldir**. Uygulama ayrıntılarına erişim önerilmez, ancak MFC sizin için kararı bırakır.

MFC kaynak dosyalarında ve MFC Uygulama Sihirbazı 'Nın oluşturduğu üstbilgi dosyalarında, bu sınıf bildirimleri dahilinde (genellikle bu sırada) gibi açıklamalar bulacaksınız:

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

Bu makale ailesinde yer almayan konular şunlardır:

- [Açıklamalara bir örnek](../mfc/an-example-of-the-comments.md)

- [Uygulama açıklaması](../mfc/decrement-implementation-comment.md)

- [//Oluşturucular yorumu](../mfc/decrement-constructors-comment.md)

- [//Öznitelikleri yorumu](../mfc/decrement-attributes-comment.md)

- [//Işlem açıklaması](../mfc/decrement-operations-comment.md)

- [//Geçersiz kılınan bir açıklama](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)
