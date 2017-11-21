---
title: "Menüler ve kaynaklar: sunucu ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDP_OLE_INIT_FAILED
dev_langs: C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- accelerator tables [MFC], server applications
- visual editing [MFC], application menus and resources
- server applications [MFC], accelerator table
- string tables [MFC], visual editing applications
- servers [MFC], menu additions
- resources [MFC], server applications
- OLE server applications [MFC], menus and resources
- string editing [MFC], visual editing applications
- IDP_OLE_INIT_FAILED macro [MFC]
- server applications [MFC], OLE menus and resources
- OLE initialization failure [MFC]
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 65417079c3241feca9c43e058026674c6e35d18b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="menus-and-resources-server-additions"></a>Menüler ve Kaynaklar: Sunucu Ekleme
Bu makalede menüleri ve diğer kaynakların bir görsel düzenleme sunucu (Bileşen) uygulaması için yapılması gereken değişiklikleri açıklar. Bu üç modlarından birini başlatılabilir çünkü sunucu uygulaması menü yapısı ve diğer kaynakları birçok eklemeleri gerektirir: tek başına, katıştırılmış, veya yerinde bildirimde. Bölümünde açıklandığı gibi [menüleri ve kaynakları (OLE)](../mfc/menus-and-resources-ole.md) makale, en fazla dört menüleri kümesi vardır. Yalnızca üç miniserver için kullanılırken dört bir MDI tam sunucu uygulaması için kullanılır. Uygulama Sihirbazı'nı menüsü düzeni istediğiniz sunucu türü için gerekli oluşturur. Bazı özelleştirme gerekli olabilir.  
  
 Uygulama Sihirbazı'nı kullanmıyorsanız HIERSVR aramak isteyebilirsiniz. RC, MFC örnek uygulama için bir kaynak betik [HIERSVR](../visual-cpp-samples.md), bu değişikliklerin nasıl uygulandığı görmek için.  
  
 Bu makalede ele alınan konular şunlardır:  
  
-   [Sunucu menüsü ekleme](#_core_server_menu_additions)  
  
-   [Hızlandırıcı tablo ekleme](#_core_server_application_accelerator_table_additions)  
  
-   [Dize tablo ekleme](../mfc/menus-and-resources-container-additions.md)  
  
-   [Miniserver eklemeler](#_core_mini.2d.server_additions)  
  
##  <a name="_core_server_menu_additions"></a>Sunucu menüsü ekleme  
 Sunucu (Bileşen) uygulamaları OLE görsel düzenleme desteklemek için eklenen menüsü kaynaklarını olması gerekir. Tek başına modunda uygulama çalıştırıldığında kullanılan menüleri değiştirilmesi gerekmez, ancak uygulamayı oluşturmadan önce iki yeni menü kaynakları eklemeniz gerekir: bir yerinde etkinleştirme ve sunucunun tam olarak açık olması desteklemek için bir desteklemek için. Her iki menüsü kaynaklarını tam ve miniserver uygulamalar tarafından kullanılır.  
  
-   Yerinde etkinleştirme desteklemek için tek başına modunda çalıştırdığınızda kullanılan menü kaynak için çok benzer bir menü kaynağı oluşturmanız gerekir. Bu menüdeki dosya ve pencere öğelerini (ve uygulama ve veri ile ilgili herhangi bir menü öğesini) eksik farktır. Kapsayıcı uygulama bu menü öğelerini kullanacaksınız. Hakkında daha fazla bilgi ve örnek olarak, bu menü birleştirme teknik için makaleyi bkz [menüler ve kaynaklar: menü birleştirme](../mfc/menus-and-resources-menu-merging.md).  
  
-   Tam olarak açık etkinleştirmeyi desteklemek için tek başına modunda çalıştırdığınızda menüsü kaynak kullanılan menü kaynak neredeyse aynı oluşturmanız gerekir. Yalnızca bu menü kaynağa bileşik bir belge içine katıştırılmış bir öğede sunucunun işletim olgu yansıtacak şekilde bazı öğeler reworded değişikliktir.  
  
 Bu makalede listelenen değişikliklerin yanı sıra, kaynak dosyanızı AFXOLESV içermesi gerekir. RC için Microsoft Foundation Class Kitaplığı uygulaması gereklidir. MFC\Include alt dizinindeki dosyasıdır.  
  
##  <a name="_core_server_application_accelerator_table_additions"></a>Sunucu uygulama Hızlandırıcı tablo ekleme  
 Sunucu uygulamaları için iki yeni Hızlandırıcı tablosu kaynaklar eklenmesi gerekir; Bunlar, daha önce açıklanan doğrudan yeni menü kaynaklara karşılık gelir. Sunucu uygulaması yerinde etkinleştirildiğinde ilk Hızlandırıcı tablosu kullanılır. Bu dosya ve pencere menüleri bağlı dışında görünümün Hızlandırıcı tablosundaki tüm girişleri oluşur.  
  
 İkinci tablo görünümün Hızlandırıcı tablosu neredeyse tam bir kopyasını ' dir. Farkları paralel belirtilen tamamen açık menüde yapılan değişiklikleri [sunucu menü eklemeleri](#_core_server_menu_additions).  
  
 Örneği bu Hızlandırıcı tablosu değişiklikleri için karşılaştırma **IDR_HIERSVRTYPE_SRVR_IP** ve **IDR_HIERSVRTYPE_SRVR_EMB** Hızlandırıcı tabloları ile **IDR_MAINFRAME** HIERSVR. MFC OLE örnekte bulunan RC dosyası [HIERSVR](../visual-cpp-samples.md). Dosya ve pencere Hızlandırıcıları yerinde tablosundan eksik ve bunları tam kopyalarını katıştırılmış tabloda yer alan.  
  
##  <a name="_core_string_table_additions_for_server_applications"></a>Sunucu uygulamaları için dize tablo ekleme  
 Yalnızca bir dize tablo ek bir sunucu uygulaması gereklidir — OLE başlatma başarısız olduğunu belirtmek için bir dize. Örnek olarak, Uygulama Sihirbazı'nın ürettiği dize tablo girişi şöyledir:  
  
|Kimlik|Dize|  
|--------|------------|  
|**IDP_OLE_INIT_FAILED**|OLE başlatma başarısız oldu. OLE kitaplıklarının sürümünün doğru olduğundan emin olun.|  
  
##  <a name="_core_mini.2d.server_additions"></a>Miniserver eklemeler  
 Yukarıda listelenenler olarak miniservers için aynı eklemeleri uygulamak tam sunucuları için. Tek başına modunda bir miniserver çalıştırılamadığı için ana menüsü çok daha küçüktür. Yalnızca bir dosya menüsü, yalnızca öğeleri çıkış içeren uygulama Sihirbazı tarafından oluşturulan ana menü sahiptir ve hakkında bilgi. Katıştırılmış ve yerinde menüleri ve Hızlandırıcıları miniservers için tam sunucuları için aynıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menüler ve kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)   
 [Menüler ve kaynaklar: menü birleştirme](../mfc/menus-and-resources-menu-merging.md)

