---
title: "MFC veritabanı uygulamasında Dosya menüsü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51f630f5a3fe1ee5833ac2796ff2acb1841af4c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="file-menu-in-an-mfc-database-application"></a>MFC Veritabanı Uygulamasında Dosya Menüsü
MFC veritabanı uygulama oluşturma ve seri hale getirme kullanmayın, Dosya menüsünden nasıl, açık, Kapat yorumlama, kaydetme ve Farklı Kaydet komutları bu soruyu hiçbir Stil Kılavuzu olsa da, bazı öneriler şunlardır:  
  
-   Dosya menüsünde Aç komutu tamamen ortadan kaldırır.  
  
-   "Veritabanı Aç" olarak Aç komutu yorumlar ve kullanıcı uygulamanızın tanıdığı veri kaynaklarının listesini gösterir.  
  
-   Belki de "profili açın." Aç komutu yorumlama Seri hale getirilmiş bir dosyanın açılması ancak dosya kaldırmalıdır dahil olmak üzere kullanıcının tercihlerini gibi "kullanıcı profili" bilgileri içeren serileştirilmiş bir belge depolamak için kullanır veya (isteğe bağlı olarak parola dışında) her oturum açma kimliği ve veri kaynağı çözemiyorsa en açık bekletmeyi kısa süre önce kullanmış.  
  
 MFC Uygulama Sihirbazı'nı hiçbir belge ilgili dosya menü komutları ile uygulama oluşturma destekler. Seçin **veritabanı görünümü dosya desteği olmadan** seçeneği **veritabanı desteği** sayfası.  
  
 Özel bir yolla dosya menü komutu yorumlamak için bir veya daha fazla komut işleyicileri, çoğunlukla kılmalı, `CWinApp`-türetilmiş sınıf. Örneğin, tamamen geçersiz kılarsanız `OnFileOpen` (hangi uygular `ID_FILE_OPEN` komutu) anlamına gelir "Veritabanı Aç:"  
  
-   Temel sınıf sürümü çağrısı yok `OnFileOpen`, komutun framework'ün varsayılan uygulaması tamamen değiştirdiğiniz beri.  
  
-   İşleyici, bunun yerine veri kaynakları listeleyen bir iletişim kutusu görüntülemek için kullanın. Çağırarak bu tür bir iletişim kutusu görüntüleyebilir `CDatabase::OpenEx` veya `CDatabase::Open` parametresiyle **NULL**. Bu, kullanıcının makinesinde tüm kullanılabilir veri kaynakları gösteren bir ODBC iletişim kutusu açılır.  
  
-   Veritabanı uygulamaları genellikle tüm belge kaydetme nedeni büyük olasılıkla kaydetme kaldırmak istediğiniz ve profil bilgilerini depolamak için seri hale getirilmiş bir belge kullanmadığınız sürece uygulamaları kaydedin. Aksi takdirde, örneğin, "hareketi." Kaydet komutunu uygulayabilir. Bkz: [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md) bu komutları geçersiz kılma hakkında daha fazla bilgi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seri Hale Getirme: Seri Hale Getirme ile Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md)

