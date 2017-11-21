---
title: "MFC ActiveX denetimleri: Stok özellik sayfalarını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 04f49395959ec3b62f20716ddfb4ba7f4d89032d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma
ActiveX denetimleri ve bunları nasıl kullanacağınızı için kullanılabilir stok özellik sayfalarını anlatılmaktadır.  
  
 ActiveX denetiminde özellik sayfalarını kullanma ile ilgili daha fazla bilgi için aşağıdaki makalelere bakın:  
  
-   [MFC ActiveX denetimleri: Özellik sayfaları](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX denetimleri: Başka bir özel özellik sayfası ekleme](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC ActiveX denetimleri ile kullanmak için üç stok özellik sayfalarını sağlar: **CLSID_CColorPropPage**, **CLSID_CFontPropPage**, ve **CLSID_CPicturePropPage**. Bu sayfaları sırasıyla stok renk, yazı tipi ve resim özellikleri için bir kullanıcı arabirimi görüntüler.  
  
 Bu özellik sayfaları denetime içerecek şekilde kimlikleri özellik sayfası kimlikleri denetimin dizisi başlatan kodu ekleyin. Aşağıdaki örnekte, bu kod denetim uygulama dosyasında yer alan (. CPP), tüm üç stok özellik sayfalarını ve varsayılan özellik sayfası içerecek şekilde dizi başlatır (adlı `CMyPropPage` Bu örnekte):  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 Özellik sayısı sayfaları, buna Not `BEGIN_PROPPAGEIDS` makro, 4. Bu özellik sayfaları ActiveX denetimi tarafından desteklenen sayısını temsil eder.  
  
 Bu değişiklikleri yaptıktan sonra projenizi yeniden derleyin. Denetim yazı tipi, resim ve renk özellikler için özellik sayfaları artık sahiptir.  
  
> [!NOTE]
>  Denetim stok özellik sayfalarını erişilemiyorsa MFC DLL (MFCxx.DLL) geçerli işletim sistemi düzgün kaydedilmemiş olabilir. Bu, genellikle şu anda çalışan olandan farklı bir işletim sistemi altında Visual C++ yükleme sonuçlanır.  
  
> [!TIP]
>  Stok özellik sayfalarını görünür değilse (Önceki nota bakın), DLL için tam yol adına sahip komut satırından RegSvr32.exe çalıştırarak DLL'yi kaydetme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: Stok Özellikler ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md)

