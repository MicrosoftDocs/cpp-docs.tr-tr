---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: stok özellik sayfalarını kullanma'
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
ms.openlocfilehash: 37cb6e5b5dfa08c5e7935064a66c2c77fe8dcde6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133061"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma

Bu makalede, ActiveX denetimleri için kullanılabilen hisse senedi özellik sayfaları ve bunların nasıl kullanılacağı ele alınmaktadır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

ActiveX denetiminde Özellik sayfaları kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [MFC ActiveX denetimleri: Özellik sayfaları](mfc-activex-controls-property-pages.md)

- [MFC ActiveX denetimleri: başka bir özel özellik sayfası ekleme](mfc-activex-controls-adding-another-custom-property-page.md)

MFC, ActiveX denetimleriyle kullanılmak üzere üç hisse senedi özellik sayfası sağlar: `CLSID_CColorPropPage` , `CLSID_CFontPropPage` ve `CLSID_CPicturePropPage` . Bu sayfalar, stok rengi, yazı tipi ve resim özellikleri için sırasıyla bir kullanıcı arabirimi görüntüler.

Bu özellik sayfalarını bir denetime eklemek için kimliklerini, denetimin özellik sayfası kimliklerinin dizisini Başlatan koda ekleyin. Aşağıdaki örnekte, bu kod denetim uygulama dosyasında (. CPP), diziyi, üç hisse senedi özellik sayfası ve varsayılan özellik sayfası (Bu örnekte adlı) içerecek şekilde başlatır `CMyPropPage` :

[!code-cpp[NVC_MFC_AxOpt#21](codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

BEGIN_PROPPAGEIDS makrodaki Özellik sayfaları sayısının 4 olduğunu unutmayın. Bu, ActiveX denetimi tarafından desteklenen özellik sayfalarının sayısını temsil eder.

Bu değişiklikler yapıldıktan sonra projenizi yeniden derleyin. Denetiminiz artık yazı tipi, resim ve renk özellikleri için özellik sayfalarına sahiptir.

> [!NOTE]
> Denetim stoku özellik sayfalarına erişilemezse, bu, MFC DLL 'inin (MFCxx.DLL) geçerli işletim sistemiyle düzgün şekilde kaydedilmediği için olabilir. Bu durum genellikle, çalışmakta olan bir işletim sistemi altına Visual C++ yükleme sonucu oluşur.

> [!TIP]
> Hisse senedi özellik sayfalarınız görünür değilse (önceki nota bakın), komut satırından DLL 'ye tam yol adı ile RegSvr32.exe çalıştırarak DLL 'yi kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimleri: stok özellikleri ekleme](mfc-activex-controls-adding-stock-properties.md)
