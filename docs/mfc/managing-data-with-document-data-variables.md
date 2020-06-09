---
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
ms.openlocfilehash: 3d845b0fc3d00369d44c21c04a3fb7e3b8d6189e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618318"
---
# <a name="managing-data-with-document-data-variables"></a>Belge Verisi Değişkenleri ile Verileri Yönetme

Belge sınıfınızın üye değişkenleri olarak belgenizin verilerini uygulayın. Örneğin, karalama programı, `CObList` nesne işaretçileri depolayan bağlantılı bir liste olan türünde bir veri üyesi bildirir `CObject` . Bu liste, serbest çizgi çizimi oluşturan noktaların dizilerini depolamak için kullanılır.

Belgenizin üye verilerini nasıl uyguladığınız, uygulamanızın yapısına bağlıdır. MFC, size yardımcı olmak için C++ şablonlarına dayalı koleksiyonlar da dahil olmak üzere,,, ve gibi çeşitli yaygın veri türlerini kapsülleyen sınıflarla birlikte "koleksiyon sınıfları" (diziler, listeler ve haritalar) grubu sağlar `CString` `CRect` `CPoint` `CSize` `CTime` . Bu sınıflar hakkında daha fazla bilgi için *MFC başvurusu*Içindeki [sınıf kitaplığına genel bakış](class-library-overview.md) bölümüne bakın.

Belgenizin üye verilerini tanımlarken, genellikle belge sınıfına üye işlevleri ekleyerek veri öğelerini ayarlayıp alabilir ve bunlar üzerinde diğer yararlı işlemleri gerçekleştirebilirsiniz.

Görünümleriniz belge nesnesine, oluşturma zamanında görünümünde yüklü olan görünümün işaretçisini kullanarak erişir. Üye işlevini çağırarak, görünümün üye işlevlerinde bu işaretçiyi alabilirsiniz `CView` `GetDocument` . Bu işaretçiyi kendi belge türüne dönüştürmeyi unutmayın. Daha sonra işaretçi aracılığıyla ortak belge üyelerine erişebilirsiniz.

Sık veri aktarımı doğrudan erişim gerektiriyorsa veya belge sınıfının ortak üyelerini kullanmak istiyorsanız, görünüm sınıfınızı belge sınıfının arkadaş (C++ koşullarında) yapmak isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri kullanma](using-documents.md)
