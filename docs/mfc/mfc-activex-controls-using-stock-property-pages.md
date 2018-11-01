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
ms.openlocfilehash: f31bf245e35231b6cc62497e7bbc57ff7f0e6af1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545398"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma

Bu makalede, stok özellik sayfalarını ActiveX denetimleri ve bunların nasıl kullanılacağı açıklanmaktadır.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

ActiveX denetiminde özellik sayfalarını kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX Denetimleri: Özellik Sayfaları](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX Denetimleri: Başka Bir Özel Özellik Sayfası Ekleme](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC ActiveX denetimleri ile kullanmak için üç stok özellik sayfalarını sağlar: `CLSID_CColorPropPage`, `CLSID_CFontPropPage`, ve `CLSID_CPicturePropPage`. Bu sayfalar, sırasıyla stok renk, yazı tipi ve resim özellikleri için bir kullanıcı arabirimi görüntüler.

Bu özellik sayfaları denetime eklemek için kimlikleri denetimin özellik sayfası kimlikleri dizisi başlatan kodu ekleyin. Aşağıdaki örnekte, bu kod, Denetim uygulama dosyasında yer alan (. CPP), tüm üç stok özellik sayfalarını ve varsayılan özellik sayfası içerecek şekilde dizi başlatır (adlı `CMyPropPage` Bu örnekte):

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

Özellik Sayfaları'nda begın_proppageıds makrosu sayısı 4 olduğunu unutmayın. Bu özellik sayfaları ActiveX denetimi tarafından desteklenen sayısını temsil eder.

Bu değişiklikleri yaptıktan sonra projenizi yeniden derleyin. Denetiminiz artık özellik sayfaları için yazı tipi, resim ve color özelliklerini sahiptir.

> [!NOTE]
>  Denetim stok özellik sayfalarını erişilemiyorsa, MFC DLL (MFCxx.DLL) geçerli işletim sistemi düzgün kaydedilmemiş olabilir. Bu, genellikle Visual C++'ı yükleme şu anda çalışan farklı bir işletim sistemi altında olur.

> [!TIP]
>  Değilse, stok özellik sayfalarını görünür (Önceki nota bakın), DLL Dosyasının tam yol adı ile komut satırından RegSvr32.exe DLL'ye çalıştırarak kaydedin.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Stok Özellikler Ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md)

