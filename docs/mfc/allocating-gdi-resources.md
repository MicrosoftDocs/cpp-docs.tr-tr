---
title: GDI Kaynaklarını Ayırma
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: 149aefeade6f99c294b12bfb294cdf1addb9e5e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370847"
---
# <a name="allocating-gdi-resources"></a>GDI Kaynaklarını Ayırma

Bu makalede, yazdırma için gereken Windows grafik aygıtı arabirimi (GDI) nesnelerinin nasıl tahsis edilip dağıtıldırı açıklanmaktadır.

> [!NOTE]
> Daha fazla bilgi için [GDI+ SDK belgelerine](/windows/win32/gdiplus/-gdiplus-gdi-start)bakın.

Yazdırma kullanabilirsiniz, ancak ekran ekranı için değil, yazdırmak için belirli yazı tiplerini, kalemleri veya diğer GDI nesnelerini kullanmanız gerektiğini varsayalım. Gereksinim duydukları bellek nedeniyle, uygulama başlatıldığında bu nesneleri ayırmak verimsizdir. Uygulama bir belgeyi yazdırmıyorsa, bu bellek başka amaçlar için gerekli olabilir. Yazdırma başladığında bunları ayırmak ve yazdırma sona erdiğinde silmek daha iyidir.

Bu GDI nesnelerini ayırmak için [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) üye işlevini geçersiz kılın. Bu işlev iki nedenden dolayı bu amaca uygundur: çerçeve her yazdırma işinin başında bu işlevi bir kez çağırır ve [OnPreparePrinting'in](../mfc/reference/cview-class.md#onprepareprinting)aksine, bu işlev yazıcı aygıtı sürücüsünü temsil eden [CDC](../mfc/reference/cdc-class.md) nesnesine erişebilir. GDI nesnelerini (örneğin, `CFont *` üyeler vb.) işaret eden görünüm sınıfınızdaki üye değişkenleri tanımlayarak bu nesneleri yazdırma işi sırasında kullanılmak üzere depolayabilirsiniz.

Oluşturduğunuz GDI nesnelerini kullanmak için, [bunları OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevindeki yazıcı aygıtı bağlamına seçin. Belgenin farklı sayfaları için farklı GDI nesnelerine ihtiyacınız `m_nCurPage` varsa, [CPrintInfo](../mfc/reference/cprintinfo-structure.md) yapısının üyesini inceleyebilir ve GDI nesnesini buna göre seçebilirsiniz. Birkaç ardışık sayfa için bir GDI nesnesine ihtiyacınız varsa, Windows `OnPrint` aygıtı her çağrıldığında aygıt bağlamına seçmeniz gerekir.

Bu GDI nesnelerini dağıtmak için [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) üye işlevini geçersiz kılın. Çerçeve, her yazdırma işinin sonunda bu işlevi çağırır ve uygulama diğer görevlere dönmeden önce yazdırmaya özgü GDI nesnelerini bulma fırsatı verir.

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](../mfc/printing.md)<br/>
[Varsayılan Yazdırma Nasıl Yapılır?](../mfc/how-default-printing-is-done.md)
