---
description: 'Daha fazla bilgi edinin: kapsayıcılar: bileşik dosyalar'
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
ms.openlocfilehash: d7c7d62569575890afd0f28b803c813a3576f627
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310427"
---
# <a name="containers-compound-files"></a>Kapsayıcılar: Bileşik Dosyalar

Bu makalede, bileşik dosyaların bileşenleri ve uygulamaları ile OLE uygulamalarınızda bileşik dosyaları kullanmanın avantajları ve dezavantajları açıklanmaktadır.

Birleşik dosyalar OLE 'nin ayrılmaz bir parçasıdır. Veri aktarımını ve OLE belge depolamayı kolaylaştırmak için kullanılırlar. Bileşik dosyalar, etkin yapılandırılmış depolama modelinin bir uygulamasıdır. Depolamaya, akışa veya dosya nesnesine Serileştirmeyi destekleyen tutarlı arabirimler vardır. Bileşik dosyalar, Microsoft Foundation Class Kitaplığı ve sınıfları tarafından desteklenir `COleStreamFile` `COleDocument` .

> [!NOTE]
> Bileşik bir dosyanın kullanılması, bilgilerin bir OLE belgesinden veya bileşik bir belgeden geldiğini göstermez. Bileşik dosyalar, Birleşik belgeleri, OLE belgelerini ve diğer verileri depolamanın yalnızca biridir.

## <a name="components-of-a-compound-file"></a><a name="_core_components_of_a_compound_file"></a> Bileşik bir dosyanın bileşenleri

Bileşik dosyaların OLE uygulamasında üç nesne türü kullanılmaktadır: Stream nesneleri, depolama nesneleri ve `ILockBytes` nesneler. Bu nesneler, standart dosya sisteminin bileşenlerine benzer ve aşağıdaki yollarla benzerdir:

- Dosyalar gibi akış nesneleri, herhangi bir türdeki verileri depolar.

- Dizinler gibi depolama nesneleri, diğer depolama ve akış nesneleri içerebilir.

- `LockBytes` nesneler, depolama nesneleri ile fiziksel donanım arasındaki arabirimi temsil eder. Gerçek baytların, `LockBytes` bir sabit sürücü veya küresel bellek alanı gibi, nesnenin eriştiği depolama cihazına nasıl yazıldığını belirlarlar. Nesneler ve arabirim hakkında daha fazla bilgi için `LockBytes` `ILockBytes` bkz. *OLE Programcı başvurusu*.

## <a name="advantages-and-disadvantages-of-compound-files"></a><a name="_core_advantages_and_disadvantages_of_compound_files"></a> Bileşik dosyaların avantajları ve dezavantajları

Bileşik dosyalar, daha önceki dosya depolama yöntemleriyle sunulan avantajlar sağlar. Bunlara aşağıdakiler dahildir:

- Artımlı dosya erişimi.

- Dosya erişim modları.

- Dosya yapısını standartlaştırın.

Bileşik dosyaların olası dezavantajları — disketlerde depolama ile ilgili büyük boyut ve performans sorunları — bu uygulamaları uygulamanızda kullanıp kullanmayacağınızı saptarken göz önünde bulundurulmalıdır.

### <a name="incremental-access-to-files"></a><a name="_core_incremental_access_to_files"></a> Dosyalara artımlı erişim

Dosyalara artımlı erişim, bileşik dosyaları kullanmanın otomatik avantajıdır. Bileşik bir dosya bir "dosya içinde dosya sistemi" olarak görüntülenebildiğinden, dosyanın tamamı yüklenmeye gerek kalmadan Stream veya Storage gibi tekil nesne türlerine erişilebilir. Bu, bir uygulamanın kullanıcı tarafından düzenlenmek üzere yeni nesnelere erişmesi için gereken süreyi önemli ölçüde azaltabilir. Aynı kavramı temel alan artımlı güncelleştirme, benzer avantajlar sunmaktadır. OLE, tek bir nesneye yapılan değişiklikleri kaydetmek için dosyanın tamamını kaydetmek yerine yalnızca Kullanıcı tarafından düzenlenen akışı veya depolama nesnesini kaydeder.

### <a name="file-access-modes"></a><a name="_core_file_access_modes"></a> Dosya erişim modları

Bileşik bir dosyadaki nesnelerde yapılan değişikliklerin diske ne zaman yürütüldüğü, bileşik dosyaları kullanmanın başka bir avantajı olduğunu tespit edebiliyor. Değişikliklerin ne zaman işleneceğini, işlenen ya da doğrudan olan dosyaların eriştiği moda belirler.

- İşlem temelli mod, bileşik bir dosyadaki nesnelerde değişiklik yapmak için iki aşamalı bir işleme işlemi kullanır, böylece Kullanıcı değişiklikleri kaydetmeyi veya geri almayı seçinceye kadar belgenin hem eski hem de yeni kopyalarının kullanılabilmesini sağlar.

- Doğrudan mod, değişiklikleri, daha sonra geri alma özelliği olmadan, belgede yapılan değişikliklerle birleştirir.

Erişim modları hakkında daha fazla bilgi için bkz. *OLE Programcı başvurusu*.

### <a name="standardization"></a><a name="_core_standardization"></a> Sürecinden

Bileşik dosyaların standartlaştırılmış yapısı, farklı OLE uygulamalarının, dosyayı gerçekten oluşturan uygulamayla ilgili hiçbir bilgi olmadan OLE uygulamanız tarafından oluşturulan bileşik dosyalara gözatmasına olanak tanır.

### <a name="size-and-performance-considerations"></a><a name="_core_size_and_performance_considerations"></a> Boyut ve performans konuları

Bileşik dosya depolama yapısının karmaşıklığı ve verileri artımlı olarak kaydetme yeteneği nedeniyle, bu biçimi kullanan dosyalar, yapılandırılmamış veya "düz dosya" depolama alanı kullanılarak diğer dosyalardan daha büyük olur. Uygulamanız sıklıkla dosya yüklerse ve kaydederse, bileşik dosyaları kullanmak dosya boyutunun, bileşik olmayan dosyalardan çok daha hızlı artmasına neden olabilir. Bileşik dosyalar büyük olabileceğinden, disketlerden depolanan ve bu disklere yüklenen dosyalar için erişim süresi de etkilenebilir, böylece dosyalara daha yavaş erişim elde edilir.

Performansı etkileyen bir diğer sorun da bileşik dosya parçalanması ' dir. Bileşik bir dosyanın boyutu, dosya tarafından kullanılan ilk ve son disk kesimleri arasındaki farka göre belirlenir. Parçalanmış bir dosya, veri içermeyen çok sayıda boş alan içerebilir, ancak boyut hesaplanırken sayılır. Bileşik bir dosyanın ömrü boyunca, bu bölgeler depolama nesneleri ekleme veya silme işlemi tarafından oluşturulur.

## <a name="using-compound-files-format-for-your-data"></a><a name="_core_using_compound_files_format_for_your_data"></a> Verileriniz için bileşik dosya biçimi kullanma

Öğesinden türetilmiş bir belge sınıfına sahip olan bir uygulamayı başarıyla oluşturduktan sonra `COleDocument` , ana belge oluşturucunun çağrı yapıldığından emin olun `EnableCompoundFile` . Uygulama Sihirbazı OLE kapsayıcı uygulamaları oluşturduğunda, bu çağrı sizin için eklenir.

*OLE programcı başvurusunda*, bkz. [IStream](/windows/win32/api/objidl/nn-objidl-istream), [Isstorage](/windows/win32/api/objidl/nn-objidl-istorage)ve [ılockbayt](/windows/win32/api/objidl/nn-objidl-ilockbytes).

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](containers.md)<br/>
[Kapsayıcılar: User-Interface sorunları](containers-user-interface-issues.md)<br/>
[Cotastreamfile sınıfı](reference/colestreamfile-class.md)<br/>
[Cotadocument sınıfı](reference/coledocument-class.md)
