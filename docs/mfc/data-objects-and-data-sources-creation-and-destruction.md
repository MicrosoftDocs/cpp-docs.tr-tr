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
ms.openlocfilehash: c5bbc2b3e19278a397e13c9b936d2434570c581c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127435"
---
# <a name="data-objects-and-data-sources-creation-and-destruction"></a>Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme

Veri nesneleri [ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)makalesinde açıklandığı gibi veri nesneleri ve veri kaynakları, veri aktarımının her iki tarafını da temsil eder. Bu makalede aşağıdakiler de dahil olmak üzere, veri aktarımlarını doğru şekilde gerçekleştirmek için bu nesne ve kaynakları oluşturma ve yok etme işlemleri açıklanmaktadır:

- [Veri nesneleri oluşturma](#_core_creating_data_objects)

- [Veri nesnelerini yok etme](#_core_destroying_data_objects)

- [Veri kaynakları oluşturma](#_core_creating_data_sources)

- [Veri kaynaklarını yok etme](#_core_destroying_data_sources)

##  <a name="_core_creating_data_objects"></a>Veri nesneleri oluşturma

Veri nesneleri, hedef uygulama tarafından, istemci ya da sunucu tarafından kullanılır. Hedef uygulamadaki bir veri nesnesi, kaynak uygulamayla hedef uygulama arasında bir bağlantının bir sonu olur. Hedef uygulamadaki bir veri nesnesi, veri kaynağındaki verilere erişmek ve bu verilerle etkileşim kurmak için kullanılır.

Bir veri nesnesi gereken iki yaygın durum vardır. İlk durum, sürükle ve bırak kullanılarak uygulamanızda verilerin bırakılmakta olduğu durumdur. İkinci durum, düzenleme menüsünde Özel Yapıştır veya Yapıştır ' ın seçildiği durumdur.

Bir sürükle ve bırak durumunda veri nesnesi oluşturmanız gerekmez. Var olan bir veri nesnesine yönelik bir işaretçi `OnDrop` işlevinizi geçirilecek. Bu veri nesnesi, sürükle ve bırak işleminin bir parçası olarak Framework tarafından oluşturulur ve ayrıca onun tarafından yok edilir. Yapıştırma başka bir yöntem tarafından yapıldığında bu her zaman durum değildir. Daha fazla bilgi için bkz. [veri nesnelerini yok](#_core_destroying_data_objects)etme.

Uygulama Paste veya Paste özel işlemi yapıyorsa, bir `COleDataObject` nesnesi oluşturmanız ve `AttachClipboard` üye işlevini çağırmanız gerekir. Bu, veri nesnesini panodaki verilerle ilişkilendirir. Daha sonra bu veri nesnesini, yapıştırma işlevinizde kullanabilirsiniz.

##  <a name="_core_destroying_data_objects"></a>Veri nesnelerini yok etme

[Veri nesneleri oluşturma](#_core_creating_data_objects)bölümünde açıklanan düzeni izlerseniz veri nesnelerinin yok edilmesi, veri aktarımlarının önemsiz bir yönüdür. Yapıştırma işleviniz döndüğünde, yapıştırma işlevinizde oluşturulan veri nesnesi MFC tarafından yok edilir.

Yapıştırma işlemlerini işlemeye yönelik başka bir yöntemi izlerseniz, yapıştırma işleminizi tamamladıktan sonra veri nesnesinin yok edildiğinden emin olun. Veri nesnesi yok edilene kadar herhangi bir uygulamanın, verileri panoya başarıyla kopyalaması olanaksız olacaktır.

##  <a name="_core_creating_data_sources"></a>Veri kaynakları oluşturma

Veri kaynakları, veri aktarımının istemcisi ya da sunucu tarafı olabilen veri aktarımının kaynağı tarafından kullanılır. Kaynak uygulamadaki bir veri kaynağı, kaynak uygulamayla hedef uygulama arasındaki bağlantının bir bitişdir. Hedef uygulamadaki veri nesnesi, veri kaynağındaki verilerle etkileşim kurmak için kullanılır.

Veri kaynakları, bir uygulamanın panoya veri kopyalaması gerektiğinde oluşturulur. Tipik bir senaryo şöyle çalışır:

1. Kullanıcı bazı verileri seçer.

1. Kullanıcı **düzenleme** menüsünden **Kopyala** (veya **Kes**) öğesini seçer veya bir sürükle ve bırak işlemi başlatır.

1. Uygulama, programın tasarımına bağlı olarak, bir `COleDataSource` nesnesi veya `COleDataSource`türetilmiş bir sınıftan bir nesne oluşturur.

1. Seçilen veriler, `COleDataSource::CacheData` veya `COleDataSource::DelayRenderData` gruplarındaki işlevlerden birini çağırarak veri kaynağına eklenir.

1. Uygulama, adım 3 ' te oluşturulan nesneye ait olan `SetClipboard` üye işlevini (veya bir sürükle ve bırak işlemi ise `DoDragDrop` üye işlevini) çağırır.

1. Bu bir **kesme** işlemidir veya `DoDragDrop` **DROPEFFECT_MOVE**döndürürse, 1. adımda seçilen veriler belgeden silinir.

Bu senaryo MFC OLE örnekleri [Oclient](../overview/visual-cpp-samples.md) ve [hiersvr](../overview/visual-cpp-samples.md)tarafından uygulanır. Her uygulamanın `CView`türetilmiş sınıfının kaynağına, `GetClipboardData` ve `OnGetClipboardData` işlevlerine bakın. Bu iki işlev `COleClientItem` ya da `COleServerItem`türetilmiş sınıf uygulamalarında bulunur. Bu örnek programlar, bu kavramların nasıl uygulanacağını gösteren iyi bir örnek sağlar.

Bir sürükle ve bırak işleminin varsayılan davranışını değiştiriyorsanız `COleDataSource` nesne oluşturmak isteyebileceğiniz başka bir durum oluşur. Daha fazla bilgi için bkz. [OLE sürükle ve bırak: özelleştirme sürükle ve bırak](../mfc/drag-and-drop-ole.md#customize-drag-and-drop) makalesi.

##  <a name="_core_destroying_data_sources"></a>Veri kaynaklarını yok etme

Veri kaynaklarının Şu anda sorumlu olan uygulama tarafından yok edilmesi gerekir. Veri kaynağını OLE 'ye ( [Cotadatasource::D oDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)) çağırma gibi durumlarda, `pDataSrc->InternalRelease`çağırmanız gerekir. Örneğin:

[!code-cpp[NVC_MFCListView#1](../atl/reference/codesnippet/cpp/data-objects-and-data-sources-creation-and-destruction_1.cpp)]

Veri kaynağınızı OLE 'ye getiryapmadıysanız, herhangi bir normal C++ nesne gibi, yok edilirken yok etmeniz sorumludur.

Daha fazla bilgi için bkz. [sürükleme ve bırakma](../mfc/drag-and-drop-ole.md), [Pano](../mfc/clipboard.md)ve [veri nesnelerini ve veri kaynaklarını düzenleme](../mfc/data-objects-and-data-sources-manipulation.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject Sınıfı](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
