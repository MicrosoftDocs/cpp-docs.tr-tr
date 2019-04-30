---
title: Yazdırma
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: e0cd2d6d85cb9820b23495a003068994b13f9c85
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339581"
---
# <a name="printing"></a>Yazdırma

CİHAZDAN bağımsız görüntü Microsoft Windows uygular. MFC içinde aynı çizim çağrıları, yani `OnDraw` çizim ekranı ve yazıcılar gibi diğer cihazları sorumlu görünümü sınıfınızın bir üye işlevi. Baskı Önizleme için görüntülenecek sanal yazıcı çıktı hedef cihazdır.

##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> Framework'ün rol karşılaştırması yazdırmada rolünüz

Görünüm sınıfınıza aşağıdaki sorumluluklara sahiptir:

- Framework, belgede kaç sayfalarıdır bildirin.

- Belirtilen bir sayfa yazdırmak için sorulduğunda, bu kısmını serileştirmeniz çizin.

- Ayırma ve tüm yazı tiplerini veya yazdırma için gerekli diğer grafik cihaz arabirimi (GDI) kaynaklarını serbest bırakın.

- Gerekirse, tüm gönderme çıkış kodları, örneğin belirli bir sayfa yazdırmadan önce yazıcı modu değiştirmek için sayfa başına temelinde Yazdırma yönünü değiştirmek için gerekli.

Framework'ün Sorumluluklar aşağıdaki gibidir:

- Görüntü **yazdırma** iletişim kutusu.

- Oluşturma bir [CDC](../mfc/reference/cdc-class.md) yazıcı nesnesi.

- Çağrı [StartDoc](../mfc/reference/cdc-class.md#startdoc) ve [EndDoc](../mfc/reference/cdc-class.md#enddoc) üye işlevleri `CDC` nesne.

- Tekrar tekrar çağırmak [StartPage](../mfc/reference/cdc-class.md#startpage) üye işlevinin `CDC` nesne, hangi sayfa yazdırılıp ve arama görünüm sınıfını bildirin [EndPage](../mfc/reference/cdc-class.md#endpage) üye işlevinin `CDC` nesne.

- Geçersiz kılınabilir işlevler görünümünde uygun zamanlarda çağırın.

Aşağıdaki makaleler framework yazdırmayı ve baskı önizlemeyi nasıl desteklediği açıklanmaktadır:

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Varsayılan yazdırmayı yapma](../mfc/how-default-printing-is-done.md)

- [Birden fazla belge](../mfc/multipage-documents.md)

- [Üstbilgiler ve altbilgiler](../mfc/headers-and-footers.md)

- [Yazdırma için GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)

- [Baskı Önizleme](../mfc/print-preview-architecture.md)

## <a name="see-also"></a>Ayrıca bkz.

[{1&gt;Yazdırma ve yazdırma önizleme&lt;1}](../mfc/printing-and-print-preview.md)
