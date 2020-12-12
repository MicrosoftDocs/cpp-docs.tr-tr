---
description: 'Veri nesneleri ve veri kaynakları hakkında daha fazla bilgi edinin: oluşturma ve yok etme'
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
ms.openlocfilehash: a19c7c2125c7d591bc4df4b3f01553a54de6a18b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206194"
---
# <a name="data-objects-and-data-sources-creation-and-destruction"></a>Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme

Veri nesneleri [ve veri kaynakları (OLE)](data-objects-and-data-sources-ole.md)makalesinde açıklandığı gibi veri nesneleri ve veri kaynakları, veri aktarımının her iki tarafını da temsil eder. Bu makalede aşağıdakiler de dahil olmak üzere, veri aktarımlarını doğru şekilde gerçekleştirmek için bu nesne ve kaynakları oluşturma ve yok etme işlemleri açıklanmaktadır:

- [Veri nesneleri oluşturma](#_core_creating_data_objects)

- [Veri nesnelerini yok etme](#_core_destroying_data_objects)

- [Veri kaynağı oluşturma](#_core_creating_data_sources)

- [Veri kaynaklarını yok etme](#_core_destroying_data_sources)

## <a name="creating-data-objects"></a><a name="_core_creating_data_objects"></a> Veri nesneleri oluşturma

Veri nesneleri, hedef uygulama tarafından, istemci ya da sunucu tarafından kullanılır. Hedef uygulamadaki bir veri nesnesi, kaynak uygulamayla hedef uygulama arasında bir bağlantının bir sonu olur. Hedef uygulamadaki bir veri nesnesi, veri kaynağındaki verilere erişmek ve bu verilerle etkileşim kurmak için kullanılır.

Bir veri nesnesi gereken iki yaygın durum vardır. İlk durum, sürükle ve bırak kullanılarak uygulamanızda verilerin bırakılmakta olduğu durumdur. İkinci durum, düzenleme menüsünde Özel Yapıştır veya Yapıştır ' ın seçildiği durumdur.

Bir sürükle ve bırak durumunda veri nesnesi oluşturmanız gerekmez. İşlevinizin varolan bir veri nesnesi işaretçisi geçirilecek `OnDrop` . Bu veri nesnesi, sürükle ve bırak işleminin bir parçası olarak Framework tarafından oluşturulur ve ayrıca onun tarafından yok edilir. Yapıştırma başka bir yöntem tarafından yapıldığında bu her zaman durum değildir. Daha fazla bilgi için bkz. [veri nesnelerini yok](#_core_destroying_data_objects)etme.

Uygulama Paste veya Paste özel işlemi yapıyorsa, bir `COleDataObject` nesnesi oluşturmalı ve onun `AttachClipboard` üye işlevini çağırmalısınız. Bu, veri nesnesini panodaki verilerle ilişkilendirir. Daha sonra bu veri nesnesini, yapıştırma işlevinizde kullanabilirsiniz.

## <a name="destroying-data-objects"></a><a name="_core_destroying_data_objects"></a> Veri nesnelerini yok etme

[Veri nesneleri oluşturma](#_core_creating_data_objects)bölümünde açıklanan düzeni izlerseniz veri nesnelerinin yok edilmesi, veri aktarımlarının önemsiz bir yönüdür. Yapıştırma işleviniz döndüğünde, yapıştırma işlevinizde oluşturulan veri nesnesi MFC tarafından yok edilir.

Yapıştırma işlemlerini işlemeye yönelik başka bir yöntemi izlerseniz, yapıştırma işleminizi tamamladıktan sonra veri nesnesinin yok edildiğinden emin olun. Veri nesnesi yok edilene kadar herhangi bir uygulamanın, verileri panoya başarıyla kopyalaması olanaksız olacaktır.

## <a name="creating-data-sources"></a><a name="_core_creating_data_sources"></a> Veri kaynakları oluşturma

Veri kaynakları, veri aktarımının istemcisi ya da sunucu tarafı olabilen veri aktarımının kaynağı tarafından kullanılır. Kaynak uygulamadaki bir veri kaynağı, kaynak uygulamayla hedef uygulama arasındaki bağlantının bir bitişdir. Hedef uygulamadaki veri nesnesi, veri kaynağındaki verilerle etkileşim kurmak için kullanılır.

Veri kaynakları, bir uygulamanın panoya veri kopyalaması gerektiğinde oluşturulur. Tipik bir senaryo şöyle çalışır:

1. Kullanıcı bazı verileri seçer.

1. Kullanıcı **düzenleme** menüsünden **Kopyala** (veya **Kes**) öğesini seçer veya bir sürükle ve bırak işlemi başlatır.

1. Uygulama, programın tasarımına bağlı olarak, `COleDataSource` öğesinden türetilmiş bir sınıftan bir nesne veya nesne oluşturur `COleDataSource` .

1. Seçilen veriler, veya gruplarındaki işlevlerden birini çağırarak veri kaynağına eklenir `COleDataSource::CacheData` `COleDataSource::DelayRenderData` .

1. Uygulama, `SetClipboard` `DoDragDrop` Adım 3 ' te oluşturulan nesneye ait üye işlevini (veya bir sürükle ve bırak işlemi ise üye işlevini) çağırır.

1. Bu bir **kesme** işlemi ise veya `DoDragDrop` **DROPEFFECT_MOVE** döndürürse, adım 1 ' de seçilen veriler belgeden silinir.

Bu senaryo MFC OLE örnekleri [Oclient](../overview/visual-cpp-samples.md) ve [hiersvr](../overview/visual-cpp-samples.md)tarafından uygulanır. Her uygulamanın `CView` türetilmiş sınıfının kaynağına, `GetClipboardData` ve `OnGetClipboardData` işlevlerine bakın. Bu iki işlev, `COleClientItem` ya da `COleServerItem` türetilmiş sınıf uygulamalarında bulunur. Bu örnek programlar, bu kavramların nasıl uygulanacağını gösteren iyi bir örnek sağlar.

Bir `COleDataSource` sürükle ve bırak işleminin varsayılan davranışını değiştiriyorsanız, nesne oluşturmak isteyebileceğiniz başka bir durum oluşur. Daha fazla bilgi için bkz. [OLE sürükle ve bırak: özelleştirme sürükle ve bırak](drag-and-drop-ole.md#customize-drag-and-drop) makalesi.

## <a name="destroying-data-sources"></a><a name="_core_destroying_data_sources"></a> Veri kaynaklarını yok etme

Veri kaynaklarının Şu anda sorumlu olan uygulama tarafından yok edilmesi gerekir. Veri kaynağını OLE 'ye, [Cotadatasource::D oDragDrop](reference/coledatasource-class.md#dodragdrop)gibi çağırma gibi durumlarda çağırmanız gerekir `pDataSrc->InternalRelease` . Örneğin:

[!code-cpp[NVC_MFCListView#1](../atl/reference/codesnippet/cpp/data-objects-and-data-sources-creation-and-destruction_1.cpp)]

Veri kaynağınızı OLE 'ye getiryapmadıysanız, herhangi bir normal C++ nesnesinde olduğu gibi onu yok etmeniz sizin sorumluluğunuzdadır.

Daha fazla bilgi için bkz. [sürükleme ve bırakma](drag-and-drop-ole.md), [Pano](clipboard.md)ve [veri nesnelerini ve veri kaynaklarını düzenleme](data-objects-and-data-sources-manipulation.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri nesneleri ve veri kaynakları (OLE)](data-objects-and-data-sources-ole.md)<br/>
[Cotadataobject sınıfı](reference/coledataobject-class.md)<br/>
[Cotadatasource sınıfı](reference/coledatasource-class.md)
