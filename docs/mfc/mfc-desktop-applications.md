---
title: "MFC Masaüstü uygulamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MFC
- mfc
dev_langs:
- C++
helpviewer_keywords:
- libraries, MFC
- class libraries, MFC
- MFC, about MFC
ms.assetid: 7101cb18-a681-495c-8f2b-069ad20c72f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c5f99270afc1f603b8e5e44a23cd422f96558efb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-desktop-applications"></a>MFC Masaüstü Uygulamaları
Microsoft Foundation Class (MFC) kitaplığı, nesne yönelimli bir sarmalayıcı çoğunu Win32 ve COM API'leri sağlar. Çok basit Masaüstü uygulamaları oluşturmak için kullanılır ancak, birden çok denetimleri ile daha karmaşık kullanıcı arabirimleri geliştirmek gerektiğinde en yararlı olur. MFC uygulamaları Office stili kullanıcı arabirimleri ile oluşturmak için kullanabilirsiniz.  
  
 MFC başvurusu sınıfları, genel işlevler, genel değişkenler ve Microsoft Foundation Class Kitaplığı yapmak makroları kapsar.  
  
 Her sınıf ile dahil tek tek hiyerarşi grafikler, temel sınıflar bulmak için kullanışlıdır. MFC başvurusu genellikle devralınan üye işlevleri tanımlamaz veya işleçleri devralınabilir. Bu işlevler hakkında daha fazla bilgi için hiyerarşi şemalarda temel sınıflar bakın.  
  
 Her sınıf belgeleri sınıfına genel bakış, kategori ve konuları üye işlevleri, aşırı yüklenmiş işleçler ve veri üyeleri için üye özeti içerir.  
  
 Genel ve korumalı sınıf üyeleri yalnızca normal uygulama programlarda kullanıldığında, bunların belgelenen veya türetilmiş sınıfları. Sınıf üyeleri tam listesi için sınıf üstbilgi dosyalarına bakın.  
  
> [!IMPORTANT]
>  MFC sınıfları ve üyeleri Windows çalışma zamanı ortamında yürütme uygulamaları kullanılamaz.  
>   
>  MFC kitaplıkları (dll) birden çok baytlı karakter (MBCS) kodlama için artık Visual Studio'da bulunan, ancak bir Visual Studio eklentisi kullanılabilir. Daha fazla bilgi için bkz: [MFC MBCS DLL eklentisi](mfc-mbcs-dll-add-on.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Kavramları](mfc-concepts.md)  
 MFC konuları kavramsal makalelerini.  
  
 [Hiyerarşi Grafiği](hierarchy-chart.md)  
 Görsel olarak sınıf ilişkileri Sınıf Kitaplığı'nda ayrıntılı olarak açıklanmaktadır.  
  
 [Sınıfa genel bakış](class-library-overview.md)  
 MFC Kitaplığı kategoriye göre sınıflarda listeler.  
  
 [İzlenecek Yollar](walkthroughs-mfc.md)  
 MFC Kitaplığı özelliklerle ilişkili çeşitli görevleri rehberlik makaleleri içerir.  
  
 [Teknik notlar](mfc-technical-notes.md)  
 MFC geliştirme ekibi sınıf kitaplığı tarafından yazılan özel konulara bağlantılar sağlar.  
  
 [MFC için Özelleştirme](customization-for-mfc.md)  
 MFC uygulamanız özelleştirmek için bazı ipuçları verilmektedir.  
  
 [Sınıflar](reference/mfc-classes.md)  
 MFC sınıfları için üstbilgi dosya bilgileri ve bağlantılar sağlar.  
  
 [İç Sınıflar](reference/internal-classes.md)  
 MFC'de dahili olarak kullanılır. Tamlık için bu bölümde bu dahili sınıflar açıklanmaktadır, ancak kodunuzda doğrudan kullanılması amaçlanmamıştır.  
  
 [Makroları ve genel öğeleri](reference/mfc-macros-and-globals.md)  
 Makrolar ve genel işlevler MFC Kitaplığı'nda bağlantılar sağlar.  
  
 [Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](reference/structures-styles-callbacks-and-message-maps.md)  
 Yapılar, stiller, geri aramalar ve ileti eşlemeleri MFC Kitaplığı tarafından kullanılan bağlantılar sağlar.  
  
 [MFC Sihirbazları ve İletişim Kutuları](reference/mfc-wizards-and-dialog-boxes.md)  
 MFC uygulamaları oluşturmak için Visual Studio özellikleri Kılavuzu.  
  
 [Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)  
 UI dizeler ve iletişim kutusu düzeni gibi statik kullanıcı arabirimi verileri yönetmek için kaynak dosyalarını kullanma  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hiyerarşi Grafiği Kategorileri](hierarchy-chart-categories.md)  
 MFC hiyerarşisi grafik kategoriye göre açıklar.  
  
 [ATL/MFC sınıfları paylaşılan](../atl-mfc-shared/atl-mfc-shared-classes.md)  
 MFC ve ATL arasında paylaşılan sınıfları bağlantılar sağlar  
  
 [MFC örnekleri](../visual-cpp-samples.md)  
 MFC kullanmayı gösteren örnekler için bağlantılar sağlar.  
  
 [Visual C++ Kitaplık Başvurusu](../standard-library/cpp-standard-library-reference.md)  
 Visual C++ ile ATL, MFC, OLE DB Şablonları, C çalışma zamanı kitaplığı ve C++ Standart Kitaplığı dahil olmak üzere sağlanan çeşitli kitaplıklarına bağlantılar sağlar.  
  
 [Visual Studio'da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio.md)  
 Uygulama ya da saklı yordamlar mantık hataları düzeltmek için Visual Studio hata ayıklayıcısı kullanma için bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ve ATL](mfc-and-atl.md)
