---
title: MFC'de Unicode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- wide characters, Unicode
- Unicode [MFC], MFC
- wide characters, encoding
- strings [MFC], Unicode
- Unicode [MFC], enabling
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bc7ac9a55818022a4238565ed4309fe96f7ec058
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-in-mfc"></a>MFC'de Unicode
MFC Windows NT, Windows 2000 ve Windows XP platformlarda geniş karakter kodlama için Unicode standart destekler. Unicode uygulamaları, Windows 98 platformlarında çalıştırılamıyor.  
  
 MFC kitaplıkları Unicode sürümleri aşağıda açıklanmıştır:  
  
### <a name="static-link-libraries"></a>Statik bağlantı kitaplıkları  
  
|Sürüm|Hata ayıklama|Açıklama|  
|-------------|-----------|-----------------|  
|UAFXCW.lib, .pdb|UAFXCWD.lib, .pdb|Unicode MFC statik bağlantı kitaplığı|  
  
### <a name="dynamic-link-libraries"></a>Dinamik bağlantı kitaplıkları  
  
|Sürüm|Hata ayıklama|Açıklama|  
|-------------|-----------|-----------------|  
|MFC100U.lib, .dbg, def, .dll, .map, .pdb, .prf|MFC100UD.lib, .def, .dll, .map, .pdb|Unicode MFC içeri aktarma kitaplığı (dosya uzantılarını açıklaması için aşağıdaki notlara bakın)|  
|MFCS100U.lib, .pdb|MFCS100UD.lib, .pdb|Unicode MFC statik olarak bir uygulama ya da DLL bağlanmalıdır kodu içeren kitaplığı içeri aktarma|  
  
 **Dosya türleri**  
  
-   İçeri aktarma kitaplığı dosyaları (.lib) uzantısına sahiptir.  
  
-   Dinamik bağlantı kitaplığı dosyaları (.dll) uzantısına sahiptir.  
  
-   Modül tanımlama (.def) dosyaları bir .exe veya .dll tanımlama deyimleri içeren metin dosyalarıdır.  
  
-   Harita (.map) dosyaları bağlayıcı bir program bağlanırken kullandığı bilgileri içeren metin dosyalarıdır.  
  
-   Kitaplık (.lib) dosyaları, MFC DLL sürümleri ile birlikte kullanılır. Bu dosyalar uygulama veya DLL statik olarak bağlantılı gerekir kodunu içerir.  
  
-   Program veritabanı (.pdb) dosyaları hata ayıklama ve proje durum bilgilerini içerir.  
  
-   Visual C++ hata ayıklayıcı kullandığı bilgileri (COFF FPO ve CodeView) hata ayıklama (.dbg) dosyalarını içerir.  
  
 Adlandırma kuralları hakkında ayrıntılı bilgi için bkz: [kitaplık adlandırma kuralları](../mfc/library-naming-conventions.md).  
  
 Unicode MFC ile kullanma hakkında daha fazla bilgi için bkz: [dizeleri: Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../mfc/mfc-concepts.md)   
 [Genel MFC konuları](../mfc/general-mfc-topics.md)

