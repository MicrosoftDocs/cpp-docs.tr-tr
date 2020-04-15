---
title: Yazdırma
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: a46096592c9983d04d2122bfabb56ece9346c4bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371200"
---
# <a name="printing"></a>Yazdırma

Microsoft Windows aygıtbağımsız ekran uygular. MFC'de bu, görünüm sınıfınızın `OnDraw` üye işlevinde aynı çizim çağrılarının ekranda niçin ve yazıcılar gibi diğer aygıtlarda çizim yapılmasından sorumlu olduğu anlamına gelir. Yazdırma önizlemesi için hedef aygıt, ekrana benzetilen bir yazıcı çıkışıdır.

## <a name="your-role-in-printing-vs-the-frameworks-role"></a><a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>Baskıdaki Rolünüz ve Çerçevenin Rolü

Görünüm sınıfınızın aşağıdaki sorumlulukları vardır:

- Çerçeveyi belgede kaç sayfa olduğunu bildirin.

- Belirli bir sayfayazdırmak istendiğinde, belgenin bu bölümünü çizin.

- Yazdırma için gereken yazı tiplerini veya diğer grafik aygıtı arabirimi (GDI) kaynaklarını ayırma ve anlaşma.

- Gerekirse, yazdırma yönünü sayfa başına değiştirmek için belirli bir sayfayı yazdırmadan önce yazıcı modunu değiştirmek için gereken kaçış kodlarını gönderin.

Çerçevenin sorumlulukları şunlardır:

- **Yazdır** iletişim kutusunu görüntüleyin.

- Yazıcı için bir [CDC](../mfc/reference/cdc-class.md) nesnesi oluşturun.

- Nesnenin [StartDoc](../mfc/reference/cdc-class.md#startdoc) ve [EndDoc](../mfc/reference/cdc-class.md#enddoc) `CDC` üye işlevlerini arayın.

- Nesnenin [StartPage](../mfc/reference/cdc-class.md#startpage) üye işlevini tekrar tekrar arayın, görünüm sınıfına hangi sayfanın yazdırılması gerektiğini `CDC` bildirin ve nesnenin [EndPage](../mfc/reference/cdc-class.md#endpage) üye işlevini arayın. `CDC`

- Uygun zamanlarda görünümde geçersiz kılınabilir işlevleri çağırın.

Aşağıdaki makaleler, çerçevenin yazdırma ve yazdırma önizlemesini nasıl desteklediğini tartışır:

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Varsayılan yazdırmayı yapma](../mfc/how-default-printing-is-done.md)

- [Birden fazla belge](../mfc/multipage-documents.md)

- [Üstbilgiler ve altbilgiler](../mfc/headers-and-footers.md)

- [GDI kaynaklarını yazdırmaiçin ayırma](../mfc/allocating-gdi-resources.md)

- [Önizlemeyi yazdır](../mfc/print-preview-architecture.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma ve Yazdırma Önizlemesi](../mfc/printing-and-print-preview.md)
