---
title: GDI Kaynaklarını Ayırma
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: 672a9a2ce103ae7f53f61ae955f77276eb1d2945
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509280"
---
# <a name="allocating-gdi-resources"></a>GDI Kaynaklarını Ayırma

Bu makalede, yazdırma için gereken Windows grafik cihaz arabirimi (GDI) nesnelerini ayırma ve serbest bırakma işlemleri açıklanmaktadır.

> [!NOTE]
>  Daha fazla bilgi için bkz. [GDI+ SDK belgeleri](/windows/win32/gdiplus/-gdiplus-gdi-start).

Yazdırma için bazı yazı tiplerini, kalemleri veya diğer GDI nesnelerini kullanmanız gerektiğini varsayın, ancak ekran görüntüleme için görüntülenmez. İhtiyaç duydukları bellek nedeniyle, uygulama başlatıldığında bu nesnelerin ayrılması verimsiz bir uygulamadır. Uygulama bir belge yazdırmadığında, bu bellek başka amaçlar için de gerekebilir. Yazdırma başladığında bunları ayırmak daha iyidir ve sonra yazdırma uçları silinir.

Bu GDI nesnelerini ayırmak için [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) üye işlevini geçersiz kılın. Bu işlev, iki nedenden dolayı bu amaca uygundur: Framework, bu işlevi her bir yazdırma işinin başlangıcında bir kez çağırır ve [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)'in aksine, bu işlevin yazıcı cihazını temsil eden [CDC](../mfc/reference/cdc-class.md) nesnesine erişimi vardır Aygıt. Bu nesneleri, görünüm sınıfınıza GDI nesnelerini (örneğin, `CFont *` Üyeler vb.) işaret eden üye değişkenlerini tanımlayarak, yazdırma işi sırasında kullanabilirsiniz.

Oluşturduğunuz GDI nesnelerini kullanmak için bunları [OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevindeki yazıcı cihaz bağlamına seçin. Belgenin farklı sayfaları için farklı GDI nesnelerine ihtiyacınız varsa, `m_nCurPage` [CPrintInfo](../mfc/reference/cprintinfo-structure.md) yapısının üyesini inceleyebilir ve uygun şekilde GDI nesnesini seçebilirsiniz. Birbirini izleyen birkaç sayfa için bir GDI nesnesine ihtiyacınız varsa, Windows her `OnPrint` çağrıldığında onu cihaz bağlamına seçmenizi gerektirir.

Bu GDI nesnelerini serbest bırakmak için [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) member işlevini geçersiz kılın. Framework, her yazdırma işinin sonunda bu işlevi çağırır ve böylece uygulama diğer görevlere geri dönmesinden önce yazdırmaya özgü GDI nesnelerini serbest bırakma fırsatına sahip olursunuz.

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](../mfc/printing.md)<br/>
[Varsayılan Yazdırmayı Yapma](../mfc/how-default-printing-is-done.md)
