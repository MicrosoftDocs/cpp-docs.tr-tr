---
title: 'MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma'
ms.date: 09/12/2018
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
ms.openlocfilehash: 13a0edb72657c9ffad00dcb909019bdfe4b87e11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358210"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma

Bu makalede, ActiveX denetimleri için kullanılabilir stok özelliği sayfaları ve bunların nasıl kullanılacağı açıklanmıştır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

ActiveX denetiminde özellik sayfalarını kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX Denetimleri: Özellik Sayfaları](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC ActiveX kontrolleri ile kullanılmak üzere `CLSID_CColorPropPage`üç `CLSID_CFontPropPage`stok `CLSID_CPicturePropPage`özelliği sayfaları sağlar: , , ve . Bu sayfalar, sırasıyla stok rengi, yazı tipi ve resim özellikleri için bir kullanıcı arabirimi görüntüler.

Bu özellik sayfalarını bir denetime dahil etmek için, denetimin özellik sayfası kimliklerini n içini açan koda kimliklerini ekleyin. Aşağıdaki örnekte, denetim uygulama dosyasında bulunan bu kod (. CPP), diziyi üç stok özelliği sayfasını ve varsayılan özellik sayfasını `CMyPropPage` (bu örnekte adlandırılmış) içerecek şekilde başharfe ait hale getirmekiçin:

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

BEGIN_PROPPAGEIDS makrodaki özellik sayfalarının sayısının 4 olduğunu unutmayın. Bu, ActiveX denetimi tarafından desteklenen özellik sayfası sayısını temsil eder.

Bu değişiklikler yapıldıktan sonra projenizi yeniden oluşturun. Denetiminizde artık yazı tipi, resim ve renk özellikleri için özellik sayfaları bulunuyor.

> [!NOTE]
> Kontrol stoközelliği sayfalarına erişilemiyorsa, bunun nedeni MFC DLL'nin (MFCxx.DLL) geçerli işletim sistemine düzgün şekilde kaydedilmemiş olması olabilir. Bu genellikle Visual C++'ın şu anda çalışan işletim sisteminden farklı bir işletim sistemi altında yüklenmesinden kaynaklanır.

> [!TIP]
> Stok özellik sayfalarınız görünmüyorsa (önceki Nota bakın), Komut satırından Tam yol adı ile DLL'ye RegSvr32.exe çalıştırarak DLL'yi kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Stok Özellikler Ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md)
