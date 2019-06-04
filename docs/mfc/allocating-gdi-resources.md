---
title: GDI Kaynaklarını Ayırma
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: adfd8b19f683b82eec213890c8e1345e070ff3ec
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504625"
---
# <a name="allocating-gdi-resources"></a>GDI Kaynaklarını Ayırma

Bu makalede, ayırabilir ve yazdırma için gerekli Windows grafik cihaz arabirimi (GDI) nesneleri serbest bırakma açıklanmaktadır.

> [!NOTE]
>  Daha fazla bilgi için [GDI +'da SDK Belgeleri](/windows/desktop/gdiplus/-gdiplus-gdi-start).

Belirli bir yazı tipi, kalemler veya diğer GDI nesneleri yazdırmak için ancak ekran için kullanılacak gerektiğini varsayalım. Gereksinim duydukları bellek nedeniyle, uygulama başlatıldığında, bu nesneler ayrılacak verimli değildir. Uygulama bir belge yazdırılırken değil, bu bellek diğer amaçlar için gerekebilir. Yazdırma başladığında ayırmanız ve ardından bunları uçları yazdırırken silmek daha iyidir.

Bu GDI nesneleri ayırmak için geçersiz kılma [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) üye işlevi. Bu işlev iki nedenden dolayı bu amaç için oldukça uygundur: framework bu kez her yazdırma işi ve aksine başında sürüklerken [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), bu işlev erişimi [CDC](../mfc/reference/cdc-class.md) Yazıcı cihaz sürücüsü temsil eden nesne. GDI nesneleri işaret görünümü sınıfınızdaki üye değişkenleri tanımlama, yazdırma işi sırasında kullanmak için bu nesneleri depolayabilirsiniz (örneğin, `CFont *` üyeler vb.).

GDI nesneleri oluşturduğunuz kullanmak için yazıcı cihaz bağlamına seçmek [OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevi. Farklı GDI nesneleri farklı belge sayfaları için gerekiyorsa, inceleyebilirsiniz `m_nCurPage` üyesi [Cprintınfo](../mfc/reference/cprintinfo-structure.md) yapısı ve buna göre GDI nesneyi seçin. GDI nesnesi birden fazla ardışık sayfaları için gerekiyorsa, Windows, bu cihaz bağlamına her zaman'ı seçmesini gerektirir `OnPrint` çağrılır.

Bu GDI nesneleri serbest bırakma için geçersiz kılın [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) üye işlevi. Framework sonunda uygulamayı diğer görevlere döndürmeden önce yazdırma özgü GDI nesneleri serbest bırakma fırsatı verir, her yazdırma işi, bu işlevi çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](../mfc/printing.md)<br/>
[Varsayılan Yazdırmayı Yapma](../mfc/how-default-printing-is-done.md)
