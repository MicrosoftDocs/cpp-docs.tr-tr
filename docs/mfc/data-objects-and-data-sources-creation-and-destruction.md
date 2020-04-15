---
title: 'Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme'
ms.date: 11/04/2016
helpviewer_keywords:
- destroying data objects [MFC]
- object creation [MFC], data source objects
- data sources [MFC], and data objects
- data source objects [MFC], creating
- destruction [MFC], data sources
- data source objects [MFC], destroying
- data objects [MFC], creating
- data objects [MFC], destroying
- data sources [MFC], role
- data sources [MFC], destroying
- destruction [MFC], data objects
- data sources [MFC], creating
ms.assetid: ac216d54-3ca5-4ce7-850d-cd1f6a90d4f1
ms.openlocfilehash: 58b68ca9597fd2a03cffb2bbab327dbc72d09599
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371211"
---
# <a name="data-objects-and-data-sources-creation-and-destruction"></a>Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme

Makalede Açıklandığı gibi [Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md), veri nesneleri ve veri kaynakları bir veri aktarım her iki tarafı temsil eder. Bu makalede, veri aktarımlarınızı düzgün bir şekilde gerçekleştirmek için bu nesnelerin ve kaynakların ne zaman oluşturulup yok edilecekleri açıklanmaktadır:

- [Veri nesneleri oluşturma](#_core_creating_data_objects)

- [Veri nesnelerini yok etme](#_core_destroying_data_objects)

- [Veri kaynağı oluşturma](#_core_creating_data_sources)

- [Veri kaynaklarını yok etme](#_core_destroying_data_sources)

## <a name="creating-data-objects"></a><a name="_core_creating_data_objects"></a>Veri Nesneleri Oluşturma

Veri nesneleri hedef uygulama tarafından kullanılır — istemci veya sunucu. Hedef uygulamadaki veri nesnesi, kaynak uygulama ile hedef uygulama arasındaki bağlantının bir sonudur. Hedef uygulamasındaki bir veri nesnesi, veri kaynağındaki verilere erişmek ve bunlarla etkileşimde kullanılmak üzere kullanılır.

Bir veri nesnesi gerekli iki ortak durum vardır. İlk durum, sürükle ve bırak kullanarak uygulamanızda veri bırakıldığında olur. İkinci durum, Yapıştır veya Yapıştır Özel'in Edit menüsünden seçilmesidir.

Sürükle ve bırak durumunda, bir veri nesnesi oluşturmanız gerekmez. Varolan bir veri nesnesi için `OnDrop` bir işaretçi işlevinize geçirilir. Bu veri nesnesi sürükle ve bırak işleminin bir parçası olarak çerçeve tarafından oluşturulur ve aynı zamanda onun tarafından yok edilir. Yapıştırma başka bir yöntemle yapıldığında bu her zaman böyle değildir. Daha fazla bilgi için [bkz.](#_core_destroying_data_objects)

Uygulama bir yapıştırveya yapıştır özel işlem gerçekleştiriyorsa, `COleDataObject` bir nesne `AttachClipboard` oluşturmalı ve üye işlevini çağırmalısınız. Bu, veri nesnesini Panodaki verilerle ilişkilendirer. Daha sonra bu veri nesnesi yapıştırı işlevik kullanabilirsiniz.

## <a name="destroying-data-objects"></a><a name="_core_destroying_data_objects"></a>Veri Nesnelerini Yok Etme

[Veri Nesneleri Oluşturma'da](#_core_creating_data_objects)açıklanan düzeni izlerseniz, veri nesnelerini yok etmek veri aktarımlarının önemsiz bir yönüdür. Yapıştırma işlevinizde oluşturulan veri nesnesi, yapıştırma işleviniz döndüğünde MFC tarafından yok edilir.

Yapıştırı işlemleri işleme başka bir yöntem izlerseniz, yapıştırın işlemi tamamlandıktan sonra veri nesnesi yok olduğundan emin olun. Veri nesnesi yok edilene kadar, herhangi bir uygulamanın verileri Pano'ya başarıyla kopyalaması mümkün olmayacaktır.

## <a name="creating-data-sources"></a><a name="_core_creating_data_sources"></a>Veri Kaynakları Oluşturma

Veri kaynakları, veri aktarımının istemci veya sunucu tarafı olabilecek veri aktarım kaynağı tarafından kullanılır. Kaynak uygulamasındaki bir veri kaynağı, kaynak uygulama ile hedef uygulama arasındaki bağlantının bir ucudur. Hedef uygulamasındaki bir veri nesnesi, veri kaynağındaki verilerle etkileşim kurmak için kullanılır.

Bir uygulamanın verileri Pano'ya kopyalaması gerektiğinde veri kaynakları oluşturulur. Tipik bir senaryo şu şekilde çalışır:

1. Kullanıcı bazı verileri seçer.

1. Kullanıcı, **Edit** menüsünden **Kopyala** (veya **Kes)** seçeneğini seçer veya sürükle ve bırak işlemini başlatır.

1. Programın tasarımına bağlı olarak, uygulama bir `COleDataSource` nesne ya da türetilen bir `COleDataSource`sınıftan bir nesne oluşturur.

1. Seçili veriler, veri kaynağına, `COleDataSource::CacheData` `COleDataSource::DelayRenderData` veya gruplardaki işlevlerden biri çağrılarak eklenir.

1. Uygulama, adım `SetClipboard` 3'te `DoDragDrop` oluşturulan nesneye ait üye işlevi (veya bu bir sürükle ve bırak işlemiyse üye işlevi) çağırır.

1. Bu bir **Kesme** işlemiyse veya `DoDragDrop` **DROPEFFECT_MOVE**döndürürse, adım 1'de seçilen veriler belgeden silinir.

Bu senaryo MFC OLE örnekleri [OCLIENT](../overview/visual-cpp-samples.md) ve [HIERSVR](../overview/visual-cpp-samples.md)tarafından uygulanır. Her uygulamanın `CView`türetilmiş sınıfının kaynağına `GetClipboardData` `OnGetClipboardData` bakın. Bu iki işlev `COleClientItem` ya `COleServerItem`veya türetilmiş sınıf uygulamalarında dır. Bu örnek programlar, bu kavramların nasıl uygulanacağının iyi bir örneğini sağlar.

Bir sürükle ve bırak işleminin `COleDataSource` varsayılan davranışını değiştiriyorsanız, nesne oluşturmak isteyebileceğin başka bir durum oluşur. Daha fazla bilgi için [OLE Sürükle ve bırak'a bakın: Sürükle ve bırak](../mfc/drag-and-drop-ole.md#customize-drag-and-drop) makalesini özelleştirin.

## <a name="destroying-data-sources"></a><a name="_core_destroying_data_sources"></a>Veri Kaynaklarını Yok Etme

Veri kaynakları, şu anda bunlardan sorumlu olan uygulama tarafından yok edilmelidir. [COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)arama gibi veri kaynağını OLE'ye teslim ettiğiniz durumlarda `pDataSrc->InternalRelease`aramanız gerekir. Örneğin:

[!code-cpp[NVC_MFCListView#1](../atl/reference/codesnippet/cpp/data-objects-and-data-sources-creation-and-destruction_1.cpp)]

Veri kaynağınızı OLE'ye teslim etmediyseniz, herhangi bir tipik C++ nesnesi gibi bu kaynağı yok etmekten siz sorumlusunuz.

Daha fazla bilgi için bkz: [Sürükle ve Bırak,](../mfc/drag-and-drop-ole.md) [Pano](../mfc/clipboard.md)ve [Veri Nesnelerini ve Veri Kaynaklarını Manipüle](../mfc/data-objects-and-data-sources-manipulation.md)Etme.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject Sınıfı](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
