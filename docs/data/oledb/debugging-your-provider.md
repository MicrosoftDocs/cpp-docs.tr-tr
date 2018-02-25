---
title: "Sağlayıcınızda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c5dcca9888f22aadb629bcd79a5eb73b39cddcfa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="debugging-your-provider"></a>Sağlayıcınızda Hata Ayıklama
Sağlayıcınızda hata ayıklamanın iki yolu vardır:  
  
-   Sağlayıcıları işleminde oluşturulduğundan, OLE DB Tüketici Şablonları ve sağlayıcı adımla normalde kullanarak bazı tüketici kod oluşturabilirsiniz.  
  
-   Visual C++ ile birlikte gelen ITEST yardımcı programını kullanabilirsiniz.  
  
### <a name="to-use-the-itest-utility"></a>ITEST yardımcı programını kullanma  
  
1.  Sağlayıcı projesini açın.  
  
2.  Üzerinde **projeleri** menüsünde tıklatın **ayarları**.  
  
3.  İçinde **özellik sayfaları** iletişim kutusu, tıklatın **hata ayıklama** sekmesi.  
  
4.  İçinde **hata ayıklama oturumu için yürütülebilir** kutusunda, ITEST uygulamasını seçin.  
  
5.  Kesme noktalarını ayarlayın ve her zamanki gibi hata ayıklama.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)