---
description: 'Daha fazla bilgi edinin: GDI kaynaklarını ayırma'
title: GDI Kaynaklarını Ayırma
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: 348f1ca1eadc22dfc8ca6faa6c31bb2f8d81e51e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176814"
---
# <a name="allocating-gdi-resources"></a>GDI Kaynaklarını Ayırma

Bu makalede, yazdırma için gereken Windows grafik cihaz arabirimi (GDI) nesnelerini ayırma ve serbest bırakma işlemleri açıklanmaktadır.

> [!NOTE]
> Daha fazla bilgi için bkz. [GDI+ SDK belgeleri](/windows/win32/gdiplus/-gdiplus-gdi-start).

Yazdırma için bazı yazı tiplerini, kalemleri veya diğer GDI nesnelerini kullanmanız gerektiğini varsayın, ancak ekran görüntüleme için görüntülenmez. İhtiyaç duydukları bellek nedeniyle, uygulama başlatıldığında bu nesnelerin ayrılması verimsiz bir uygulamadır. Uygulama bir belge yazdırmadığında, bu bellek başka amaçlar için de gerekebilir. Yazdırma başladığında bunları ayırmak daha iyidir ve sonra yazdırma uçları silinir.

Bu GDI nesnelerini ayırmak için [OnBeginPrinting](reference/cview-class.md#onbeginprinting) üye işlevini geçersiz kılın. Bu işlev, iki nedenden dolayı bu amaca uygundur: Framework, bu işlevi her bir yazdırma işinin başlangıcında bir kez çağırır ve [OnPreparePrinting](reference/cview-class.md#onprepareprinting)'in aksine, bu işlevin yazıcı aygıt sürücüsünü temsil eden [CDC](reference/cdc-class.md) nesnesine erişimi vardır. Bu nesneleri, görünüm sınıfınıza GDI nesnelerini (örneğin, `CFont *` Üyeler vb.) işaret eden üye değişkenlerini tanımlayarak, yazdırma işi sırasında kullanabilirsiniz.

Oluşturduğunuz GDI nesnelerini kullanmak için bunları [OnPrint](reference/cview-class.md#onprint) üye işlevindeki yazıcı cihaz bağlamına seçin. Belgenin farklı sayfaları için farklı GDI nesnelerine ihtiyacınız varsa, `m_nCurPage` [CPrintInfo](reference/cprintinfo-structure.md) yapısının üyesini inceleyebilir ve uygun şekilde GDI nesnesini seçebilirsiniz. Birbirini izleyen birkaç sayfa için bir GDI nesnesine ihtiyacınız varsa, Windows her çağrıldığında onu cihaz bağlamına seçmenizi gerektirir `OnPrint` .

Bu GDI nesnelerini serbest bırakmak için [OnEndPrinting](reference/cview-class.md#onendprinting) member işlevini geçersiz kılın. Framework, her yazdırma işinin sonunda bu işlevi çağırır ve böylece uygulama diğer görevlere geri dönmesinden önce yazdırmaya özgü GDI nesnelerini serbest bırakma fırsatına sahip olursunuz.

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](printing.md)<br/>
[Varsayılan yazdırma işlemi nasıl yapılır?](how-default-printing-is-done.md)
