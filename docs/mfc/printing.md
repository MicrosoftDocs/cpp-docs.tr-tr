---
description: 'Daha fazla bilgi edinin: yazdırma'
title: Yazdırma
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: 0cb4455b2de27d7b609226099b00a37dc8175db6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154870"
---
# <a name="printing"></a>Yazdırma

Microsoft Windows cihazdan bağımsız görüntüleme uygular. MFC 'de, bu, Görünüm sınıfınızın üye işlevindeki aynı çizim çağrılarının, `OnDraw` ekranda ve yazıcılar gibi diğer cihazlarda çizimden sorumlu olduğu anlamına gelir. Baskı Önizleme için, hedef cihaz, ekranda sanal bir yazıcı çıktıdır.

## <a name="your-role-in-printing-vs-the-frameworks-role"></a><a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> Yazdırma ve çerçevenin rolü ile

Görünüm sınıfınız aşağıdaki sorumluluklara sahiptir:

- Belgede kaç sayfa olduğunu çerçeveye bildirin.

- Belirli bir sayfayı yazdırdığınızda, belgenin o bölümünü çizin.

- Yazdırma için gereken tüm yazı tiplerini veya diğer grafik cihaz arabirimi (GDI) kaynaklarını ayırın ve serbest bırakın.

- Gerekirse, belirli bir Sayfayı yazdırmadan önce yazıcı modunu değiştirmek için gereken çıkış kodlarını gönderin; Örneğin, yazdırma yönünü sayfa temelinde değiştirin.

Çerçevenin sorumlulukları aşağıdaki gibidir:

- **Yazdır** iletişim kutusunu görüntüleyin.

- Yazıcı için bir [CDC](reference/cdc-class.md) nesnesi oluşturun.

- Nesnenin [StartDoc](reference/cdc-class.md#startdoc) ve [EndDoc](reference/cdc-class.md#enddoc) üye işlevlerini çağırın `CDC` .

- Nesnenin [StartPage](reference/cdc-class.md#startpage) üye işlevini tekrar tekrar çağırın `CDC` , görünüm sınıfına hangi sayfanın yazdırılması gerektiğini bildirin ve nesnenin [EndPage](reference/cdc-class.md#endpage) üye işlevini çağırın `CDC` .

- Görünümde uygun zamanlarda geçersiz kılınabilir işlevleri çağırın.

Aşağıdaki makalelerde Framework 'ün yazdırma ve baskı önizlemeyi nasıl desteklediği açıklanmaktadır:

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Varsayılan yazdırmayı yapma](how-default-printing-is-done.md)

- [Birden fazla belge](multipage-documents.md)

- [Üst bilgiler ve altbilgiler](headers-and-footers.md)

- [Yazdırma için GDI kaynaklarını ayırma](allocating-gdi-resources.md)

- [Baskı Önizleme](print-preview-architecture.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma ve baskı önizleme](printing-and-print-preview.md)
