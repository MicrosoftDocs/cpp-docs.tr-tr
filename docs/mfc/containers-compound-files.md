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
ms.openlocfilehash: 98166a355fd267ecbec0a7f0cc1d18fd0b2e7cd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353583"
---
# <a name="containers-compound-files"></a>Kapsayıcılar: Bileşik Dosyalar

Bu makalede, bileşik dosyaların bileşenleri ve uygulanması ve OLE uygulamalarınızda bileşik dosyaları kullanmanın avantajları ve dezavantajları açıklanmaktadır.

Bileşik dosyalar OLE'nin ayrılmaz bir parçasıdır. Veri aktarımına ve OLE belge depolamasını kolaylaştırmak için kullanılırlar. Bileşik dosyalar, Etkin yapılandırılmış depolama modelinin bir uygulamasıdır. Depolama, akış veya dosya nesnesine serileştirmeyi destekleyen tutarlı arabirimler vardır. Bileşik dosyalar Microsoft Hazırlık Sınıf Kitaplığı'nda `COleStreamFile` `COleDocument`sınıflar tarafından desteklenir ve .

> [!NOTE]
> Bileşik dosya kullanmak, bilgilerin bir OLE belgesinden veya bileşik belgeden geldiği anlamına gelmez. Bileşik dosyalar, bileşik belgeleri, OLE belgelerini ve diğer verileri depolamanın yollarından yalnızca biridir.

## <a name="components-of-a-compound-file"></a><a name="_core_components_of_a_compound_file"></a>Bileşik Dosyanın Bileşenleri

Bileşik dosyaların OLE uygulaması üç nesne türü kullanır: akış nesneleri, depolama nesneleri ve `ILockBytes` nesneler. Bu nesneler, standart bir dosya sisteminin bileşenlerine aşağıdaki şekillerde benzer:

- Dosyaları gibi nesneleri akışı, herhangi bir türde veri depolamak.

- Dizinler gibi depolama nesneleri diğer depolama ve akış nesneleri içerebilir.

- `LockBytes`nesneler, depolama nesneleri ve fiziksel donanım arasındaki arabirimi temsil eder. Gerçek baytların, sabit disk veya genel `LockBytes` bellek alanı gibi nesnenin erişen depolama aygıtına nasıl yazıldığını belirlerler. Nesneler ve `LockBytes` `ILockBytes` arayüz hakkında daha fazla bilgi için *OLE Programcısının Başvurusu'na*bakın.

## <a name="advantages-and-disadvantages-of-compound-files"></a><a name="_core_advantages_and_disadvantages_of_compound_files"></a>Bileşik Dosyaların Avantajları ve Dezavantajları

Bileşik dosyalar, daha önceki dosya depolama yöntemleriyle kullanılamayan avantajlar sağlar. Şunları içerir:

- Artımlı dosya erişimi.

- Dosya erişim modları.

- Dosya yapısının standardizasyonu.

Disketlerde depolamayla ilgili büyük boyut ve performans sorunları olan bileşik dosyaların olası dezavantajları, uygulamanızda kullanıp kullanmamaya karar verirken göz önünde bulundurulmalıdır.

### <a name="incremental-access-to-files"></a><a name="_core_incremental_access_to_files"></a>Dosyalara Artımlı Erişim

Dosyalara artımlı erişim, bileşik dosyaları kullanmanın otomatik bir avantajıdır. Bileşik dosya "dosya içindeki dosya sistemi" olarak görüntülenebildiği için, akış veya depolama gibi tek tek nesne türlerine, dosyanın tamamını yüklemeye gerek kalmadan erişilebilir. Bu, bir uygulamanın kullanıcı tarafından düzenlemek için yeni nesnelere erişmesi gereken süreyi önemli ölçüde azaltabilir. Aynı konsepte dayanan artımlı güncelleme benzer avantajlar sunar. OLE, yalnızca tek bir nesnede yapılan değişiklikleri kaydetmek için tüm dosyayı kaydetmek yerine yalnızca kullanıcı tarafından düzenlenen akışı veya depolama nesnesini kaydeder.

### <a name="file-access-modes"></a><a name="_core_file_access_modes"></a>Dosya Erişim Modları

Bileşik dosyadaki nesnelerdeki değişikliklerin diske ne zaman kaydedildiğini belirleyebilmek, bileşik dosyaları kullanmanın başka bir yararıdır. Dosyalara erişilen ve doğrudan olarak erişilen mod, değişikliklerin ne zaman kaydedildiğini belirler.

- İşlenen mod, bileşik dosyadaki nesnelerde değişiklik yapmak için iki aşamalı bir işleme işlemi kullanır ve bu nedenle kullanıcı değişiklikleri kaydetmeyi veya geri almayı seçene kadar belgenin hem eski hem de yeni kopyalarını kullanılabilir tutar.

- Doğrudan mod, daha sonra geri alma olanağı olmadan, yapılan değişiklikleri belgeye dahil eder.

Erişim modları hakkında daha fazla bilgi için *OLE Programcısının Başvurusu'na*bakın.

### <a name="standardization"></a><a name="_core_standardization"></a>Standardizasyon

Bileşik dosyaların standartlaştırılmış yapısı, farklı OLE uygulamalarının, dosyayı oluşturan uygulama hakkında hiçbir bilgi sahibi olmadan OLE uygulamanız tarafından oluşturulan bileşik dosyalara göz atmasına olanak tanır.

### <a name="size-and-performance-considerations"></a><a name="_core_size_and_performance_considerations"></a>Boyut ve Performans Hususları

Bileşik dosya depolama yapısının karmaşıklığı ve verileri artımlı olarak kaydetme özelliği nedeniyle, bu biçimi kullanan dosyalar, yapılandırılmamış veya "düz dosya" depolama alanını kullanarak diğer dosyalardan daha büyük olma eğilimindedir. Uygulamanız sık sık dosyaları yükler ve kaydederse, bileşik dosyaları kullanmak dosya boyutunun bileşik olmayan dosyalardan çok daha hızlı artmasına neden olabilir. Bileşik dosyalar büyük olabileceğinden, disketlerde depolanan ve yüklenen dosyaların erişim süresi de etkilenebilir ve bu da dosyalara daha yavaş erişim sağlar.

Performansı etkileyen bir diğer sorun bileşik dosya parçalanmasıdır. Bileşik dosyanın boyutu, dosya tarafından kullanılan ilk ve son disk sektörleri arasındaki farka göre belirlenir. Parçalanmış bir dosya, veri içermeyen, ancak boyutu hesaplarken sayılan birçok boş alan alanı içerebilir. Bileşik dosyanın ömrü boyunca, bu alanlar depolama nesnelerinin eklenmesi veya silinmesi ile oluşturulur.

## <a name="using-compound-files-format-for-your-data"></a><a name="_core_using_compound_files_format_for_your_data"></a>Verileriniz için Bileşik Dosya Biçimini Kullanma

Türetilen bir belge sınıfı olan bir `COleDocument`uygulamayı başarıyla oluşturduktan sonra, ana belge oluşturucunun aramayaptığından `EnableCompoundFile`emin olun. Uygulama sihirbazı OLE kapsayıcı uygulamaları oluşturduğunda, bu çağrı sizin için eklenir.

*OLE Programcı'nın Referans*, [IStream](/windows/win32/api/objidl/nn-objidl-istream)bakın , [IStorage](/windows/win32/api/objidl/nn-objidl-istorage), ve [ILockBytes](/windows/win32/api/objidl/nn-objidl-ilockbytes).

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Kapsayıcılar: Kullanıcı Arabirimi Sorunları](../mfc/containers-user-interface-issues.md)<br/>
[COleStreamFile Sınıfı](../mfc/reference/colestreamfile-class.md)<br/>
[COleDocument Sınıfı](../mfc/reference/coledocument-class.md)
