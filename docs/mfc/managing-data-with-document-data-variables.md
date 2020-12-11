---
description: 'Hakkında daha fazla bilgi edinin: belge veri değişkenleriyle verileri yönetme'
title: Belge Verisi Değişkenleri ile Verileri Yönetme
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
ms.openlocfilehash: d05bfe71d080c08b3e0f3bbd416421e612b5d7ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112212"
---
# <a name="managing-data-with-document-data-variables"></a>Belge Verisi Değişkenleri ile Verileri Yönetme

Belge sınıfınızın üye değişkenleri olarak belgenizin verilerini uygulayın. Örneğin, karalama programı, `CObList` nesne işaretçileri depolayan bağlantılı bir liste olan türünde bir veri üyesi bildirir `CObject` . Bu liste, serbest çizgi çizimi oluşturan noktaların dizilerini depolamak için kullanılır.

Belgenizin üye verilerini nasıl uyguladığınız, uygulamanızın yapısına bağlıdır. MFC, size yardımcı olmak için C++ şablonlarına dayalı koleksiyonlar da dahil olmak üzere,,, ve gibi çeşitli yaygın veri türlerini kapsülleyen sınıflarla birlikte "koleksiyon sınıfları" (diziler, listeler ve haritalar) grubu sağlar `CString` `CRect` `CPoint` `CSize` `CTime` . Bu sınıflar hakkında daha fazla bilgi için *MFC başvurusu* Içindeki [sınıf kitaplığına genel bakış](class-library-overview.md) bölümüne bakın.

Belgenizin üye verilerini tanımlarken, genellikle belge sınıfına üye işlevleri ekleyerek veri öğelerini ayarlayıp alabilir ve bunlar üzerinde diğer yararlı işlemleri gerçekleştirebilirsiniz.

Görünümleriniz belge nesnesine, oluşturma zamanında görünümünde yüklü olan görünümün işaretçisini kullanarak erişir. Üye işlevini çağırarak, görünümün üye işlevlerinde bu işaretçiyi alabilirsiniz `CView` `GetDocument` . Bu işaretçiyi kendi belge türüne dönüştürmeyi unutmayın. Daha sonra işaretçi aracılığıyla ortak belge üyelerine erişebilirsiniz.

Sık veri aktarımı doğrudan erişim gerektiriyorsa veya belge sınıfının ortak üyelerini kullanmak istiyorsanız, görünüm sınıfınızı belge sınıfının arkadaş (C++ koşullarında) yapmak isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri kullanma](using-documents.md)
