---
title: 'Kapsayıcılar: Bileşik Dosyalar'
ms.date: 11/04/2016
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
ms.openlocfilehash: 5a8ba0821d92ab41a4b95fb7b2a26da63c1df285
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643279"
---
# <a name="containers-compound-files"></a>Kapsayıcılar: Bileşik Dosyalar

Bu makalede, bileşenleri ve uygulama bileşik dosyalar ve avantajları ve dezavantajları uygulamalarınızdaki OLE bileşik dosyalarını kullanarak açıklanmaktadır.

Bileşik dosyalar OLE ayrılmaz bir parçasıdır. Veri aktarımı ve OLE belge depolama kolaylaştırmak için kullanılır. Bir uygulama etkin yapılandırılmış depolama modelinin bileşik dosyalarıdır. Tutarlı arabirimleri, destek serileştirme bir depolama alanı, bir akış veya dosya nesnesi yok. Bileşik dosyalar Microsoft Foundation Class Kitaplığı ' sınıflar tarafından desteklenen `COleStreamFile` ve `COleDocument`.

> [!NOTE]
>  Bileşik dosyasını kullanarak bilgiler bir OLE belgesi ya da bir bileşik belge gelir gelmez. Bileşik dosyalar bileşik belgeler, OLE belgeleri ve diğer verileri depolamak için yöntemlerinden biridir.

##  <a name="_core_components_of_a_compound_file"></a> Bir bileşik dosyası bileşenleri

Bileşik dosyalar OLE uygulamasını üç nesne türlerini kullanır: akışı nesneleri, depolama nesneleri ve `ILockBytes` nesneleri. Bu nesneler aşağıdaki yollarla bir standart dosya sistemi bileşenlerinin benzerdir:

- Stream nesneler, dosyalar gibi her tür veriyi depolayın.

- Depolama nesneleri, dizinleri gibi diğer depolama ve akış nesneleri içerebilir.

- `LockBytes` nesneleri depolama nesneleri ve fiziksel donanım arasındaki arabirimi temsil eder. Her Depolama cihazına gerçek bayt nasıl yazılır belirlerler `LockBytes` nesne eriştiği, sabit disk veya bir bölümünü genel bellek gibi. Hakkında daha fazla bilgi için `LockBytes` nesneleri ve `ILockBytes` arabirim için bkz: *OLE Programcı Başvurusu*.

##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> Olumlu ve olumsuz yönleri bileşik dosyalar

Bileşik dosyalar, file storage'nın önceki yöntemleriyle kullanılabilir değil avantajları sağlar. Bunlara aşağıdakiler dahildir:

- Artımlı dosyasına erişim.

- Erişim modu dosya.

- Dosya yapısı Standardizasyon.

Bileşik dosyalar olası dezavantajları — disket disk depolama alanı ilgili büyük boyut ve performans sorunlarını — olması dikkate alınan olduğunda karar bunları uygulamanızda kullanıp kullanmayacağınızı.

###  <a name="_core_incremental_access_to_files"></a> Artımlı dosyalara erişim

Artımlı dosyalara erişimi bileşik dosyalarını kullanarak otomatik bir avantajdır. Bileşik bir dosya olarak "dosya sistemi" bir dosya içinde görüntülenebilir olduğundan, akış veya depolama gibi tek tek nesne türlerini dosyanın tamamı yüklemek zorunda kalmadan erişilebilir. Bu, uygulamanın kullanıcı tarafından düzenleme için yeni nesnelere erişmek için gereken süreyi önemli ölçüde düşürebilir. Artımlı güncelleştirme, temel aynı kavram üzerinde benzer avantajlar sunar. Yalnızca bir nesneye yapılan değişiklikleri kaydetmek için dosyanın tamamını kaydetmek yerine kullanıcı tarafından düzenlenmiş yalnızca akış veya depolama nesnesini OLE kaydeder.

###  <a name="_core_file_access_modes"></a> Dosya erişim modları

Nesneleri birleşik bir dosyadaki değişiklikler diske kaydedilmiş olduğunda belirlemek için bileşik dosyalar kullanmanın başka bir avantajdır. Ne zaman geçildiğinde değişiklikler yapılır, dosyaları, işlenen veya doğrudan erişilir modu belirler.

- İşlenen modu, ya değişiklikleri kaydetmeyi ya değişiklikleri geri almak kullanıcı seçene kadar hem eski hem de mevcut belgeyi yeni kopyasını dolayısıyla tutma nesneleri için birleşik bir dosyadaki değişiklikler yapmak için iki aşamalı tamamlama işlemi kullanır.

- Daha sonra geri alma olanağı yapılan olarak doğrudan modu belgeye yapılan değişiklikler içerir.

Erişim modları hakkında daha fazla bilgi için bkz. *OLE Programcı Başvurusu*.

###  <a name="_core_standardization"></a> Standartlaştırma

Standartlaştırılmış yapısı bileşik dosyaları farklı OLE uygulamalarının OLE uygulamanızla aslında dosya oluşturulan uygulamanın tarafından hiçbir bilgi oluşturulan bileşik dosyalar arasında gezinin olanak sağlar.

###  <a name="_core_size_and_performance_considerations"></a> Boyut ve performans konuları

Bileşik dosya depolama yapısı ve artımlı olarak veri kaydetme olanağı karmaşıklığı nedeniyle, bu biçimi kullanarak dosyaları diğer dosyalardan daha büyük olma eğilimindedir yapılandırılmamış kullanarak ya da "düz dosya" depolama. Bileşik dosyalarını kullanarak, uygulamanızın sık yükler ve dosyaları kaydederse noncompound dosyalardan çok daha hızlı bir şekilde artırmak dosya boyutu neden olabilir. Bileşik dosyalar büyük elde edebilirsiniz çünkü disket disklerden yüklendi ve depolanan dosyalar için erişim zamanı Ayrıca, dosyalara daha yavaş erişimle sonuçlanan etkilenebilir.

Bileşik dosyanın parçalanması performansını etkileyen başka bir sorun var. Bileşik bir dosyanın boyutu, dosya tarafından kullanılan ilk ve son disk kesimlerini arasındaki farkı tarafından belirlenir. Bir parçalanmış dosyası veri içermiyor, ancak boyutu hesaplanırken sayılır birçok alanında boş alan içerebilir. Bileşik bir dosya kullanım süresi boyunca, bu alanları ekleme veya silme işlemi depolama nesneleri tarafından oluşturulur.

##  <a name="_core_using_compound_files_format_for_your_data"></a> Verileriniz için bileşik dosyalar biçimini kullanarak

Türetilen bir belge sınıf olan başarıyla bir uygulama oluşturma sonra `COleDocument`, ana belge atladığından ProcessOrder olun `EnableCompoundFile`. OLE kapsayıcı uygulamaları Uygulama Sihirbazı oluşturur, bu çağrı için eklenir.

İçinde *OLE Programcı Başvurusu*, bkz: [IStream](/windows/desktop/api/objidl/nn-objidl-istream), [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage), ve [Ilockbytes](/windows/desktop/api/objidl/nn-objidl-ilockbytes).

## <a name="see-also"></a>Ayrıca Bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Kapsayıcılar: Kullanıcı Arabirimi Sorunları](../mfc/containers-user-interface-issues.md)<br/>
[COleStreamFile Sınıfı](../mfc/reference/colestreamfile-class.md)<br/>
[COleDocument Sınıfı](../mfc/reference/coledocument-class.md)
