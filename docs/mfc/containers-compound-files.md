---
title: 'Kapsayıcılar: Bileşik dosyaları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compound files [MFC]
- compound documents
- containers [MFC], compound files
- OLE documents [MFC], compound files
- performance [MFC], compound files
- files [MFC], compound
- standardized file structure compound files
- documents [MFC], compound
- documents [MFC], OLE
- OLE containers [MFC], compound files
- access modes for files [MFC]
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8bee847d1121a6d5da1679c29a9107c8a447ab1
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930231"
---
# <a name="containers-compound-files"></a>Kapsayıcılar: Bileşik Dosyalar
Bu makalede, bileşenleri ve uygulama bileşik dosyalar ve avantajlarını ve dezavantajlarını OLE uygulamalarınızda bileşik dosyalar açıklanmaktadır.  
  
 Bileşik dosyalar OLE ayrılmaz bir parçasıdır. Veri aktarımı ve OLE belge depolama kolaylaştırmak için kullanılır. Etkin yapılandırılmış depolama modelinin uygulaması bileşik dosyalarıdır. Tutarlı arabirimleri bu destek serileştirme bir depolama, bir akış veya bir dosya nesnesi yok. Bileşik dosyalar Microsoft Foundation Class Kitaplığı'nda sınıfları tarafından desteklenen `COleStreamFile` ve `COleDocument`.  
  
> [!NOTE]
>  Bileşik dosyasını kullanarak bilgiler OLE belge veya bileşik bir belgeden gelir gelmez. Bileşik dosyalar bileşik belgeler, OLE belgeleri ve diğer verileri depolamak için yöntemleri biridir.  
  
##  <a name="_core_components_of_a_compound_file"></a> Bileşik dosyasının bileşenleri  
 OLE uygulaması bileşik dosyaları üç nesne türlerini kullanır: akışı nesneleri, depolama nesneleri ve `ILockBytes` nesneleri. Bu nesneler aşağıdaki yollarla bir standart dosya sistemi bileşenleri için benzerdir:  
  
-   Dosyalar gibi akışı nesneleri herhangi bir türde verileri depolar.  
  
-   Depolama nesneleri dizinleri gibi diğer depolama ve akış nesnelerini içerebilir.  
  
-   `LockBytes` nesneleri depolama nesneleri ve fiziksel donanım arasındaki arabirimi temsil eder. Baytlarla ne olursa olsun depolama aygıtına nasıl yazılır belirlemek `LockBytes` nesne eriştiği, bir sabit sürücü veya genel bellek alanı gibi. Hakkında daha fazla bilgi için `LockBytes` nesneleri ve `ILockBytes` arabirim için bkz: *OLE Programcı Başvurusu*.  
  
##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> Olumlu ve olumsuz yönlerini bileşik dosyalar  
 Bileşik dosyalar yararlar kullanılamaz dosya depolama alanının önceki yöntemleri sağlar. Bunlara aşağıdakiler dahildir:  
  
-   Artımlı dosyasına erişim.  
  
-   Erişim modları dosya.  
  
-   Dosya yapısı Standartlaştırma.  
  
 Bileşik dosyalar olası dezavantajları — disketler depolama ilgili büyük boyutu ve performans sorunlarını — olması dikkate alınan olduğunda karar uygulamanızda kullanıp kullanmayacağınızı.  
  
###  <a name="_core_incremental_access_to_files"></a> Artımlı dosyalara erişim  
 Artımlı dosyalara bileşik dosyaları kullanarak otomatik bir yararı erişilebilir. Bileşik dosyası "dosya sistemi" dosya içindeki olarak görüntülenebilir çünkü akış ya da depolama gibi tek tek nesne türlerini dosyanın tamamı yüklemek zorunda kalmadan erişilebilir. Bu, uygulamanın kullanıcı tarafından düzenleme için yeni nesneler erişmesi gereken zamanı önemli ölçüde düşürebilir. Artımlı güncelleştirme, temel teklifleri benzer avantajları de aynı kavrama. Yalnızca bir nesneye yapılan değişiklikleri kaydetmek için dosyanın tamamı kaydetmek yerine OLE kullanıcı tarafından düzenlenmiş yalnızca akış veya depolama nesnesi kaydeder.  
  
###  <a name="_core_file_access_modes"></a> Dosya erişim modları  
 Bileşik dosya içindeki nesnelerde yapılan değişiklikler diske kaydedilmiş olduğunda belirlemek için bileşik dosyalar kullanmanın başka bir avantaj olmalıdır. Değişiklikler olduğunda uygulanır, dosyaları, işlenen veya doğrudan, erişilen modu belirler.  
  
-   İşlenen modu, böylece kaydetmek veya değişiklikleri geri almak kullanıcının seçmesi kadar hem eski hem de kullanılabilir belge yeni kopyalarını tutma nesnelere bileşik bir dosyada değişiklik yapmak için iki aşamalı kaydetme işlemi kullanır.  
  
-   Bunlar, daha sonra bunları geri yeteneği olmadan gerçekleştirilmediğinden doğrudan modu belgeye yapılan değişiklikler içerir.  
  
 Erişim modları hakkında daha fazla bilgi için bkz: *OLE Programcı Başvurusu*.  
  
###  <a name="_core_standardization"></a> Standartlaştırma  
 Bileşik dosyalar standartlaştırılmış yapısı bileşik dosyaları OLE uygulamanızın veya dosyayı gerçekten oluşturan uygulama tarafından hiçbir bilgi ile oluşturulan göz atmak farklı OLE uygulamaları sağlar.  
  
###  <a name="_core_size_and_performance_considerations"></a> Boyutu ve performans konuları  
 Bileşik dosya depolama yapısı ve veri artımlı olarak kaydetme yeteneği karmaşıklığı nedeniyle bu biçimi kullanarak dosyaları diğer dosyalardan daha büyük olma eğilimindedir yapılandırılmamış kullanarak ya da "düz dosya" depolama. Bileşik dosyalar kullanarak, uygulamanızın sık yükler ve dosyaları kaydederse, noncompound dosyalardan çok daha hızlı bir şekilde artırmak dosya boyutu neden olabilir. Bileşik dosyalar büyük almak için erişim zamanı depolanır ve disket disklerden yüklenen dosyalar için de, dosyalara daha yavaş erişimle sonuçlanan etkilenebilir.  
  
 Performansı etkileyen başka bir bileşik dosya parçalanması sorunudur. Bileşik dosyasının boyutu, dosya tarafından kullanılan ilk ve son disk kesimleri arasındaki farkı tarafından belirlenir. Parçalanmış dosyası veri içermiyor, ancak boyut hesaplanırken sayılır birçok boş alanları içerebilir. Bileşik dosya kullanım süresi boyunca, bu alanları ekleme veya silme işlemi depolama nesnelerinin tarafından oluşturulur.  
  
##  <a name="_core_using_compound_files_format_for_your_data"></a> Bileşik dosyalar biçimi, verileriniz için kullanma  
 Türetilen bir belge sınıfı başarıyla bir uygulama oluşturma sahip olduktan sonra `COleDocument`, ana belge Oluşturucusu çağırdığı olun `EnableCompoundFile`. Uygulama Sihirbazı'nı OLE kapsayıcı uygulamaları oluşturduğunda, bu çağrı için eklenir.  
  
 İçinde *OLE Programcı Başvurusu*, bkz: [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034), [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015), ve [ILockBytes](http://msdn.microsoft.com/library/windows/desktop/aa379238).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kapsayıcıları](../mfc/containers.md)   
 [Kapsayıcılar: Kullanıcı arabirimi sorunları](../mfc/containers-user-interface-issues.md)   
 [COleStreamFile sınıfı](../mfc/reference/colestreamfile-class.md)   
 [COleDocument Sınıfı](../mfc/reference/coledocument-class.md)
