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
ms.openlocfilehash: 756f0a3870f4b211cbc7bb40449733cf70610247
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630046"
---
# <a name="managing-data-with-document-data-variables"></a>Belge Verisi Değişkenleri ile Verileri Yönetme

Belgenizin veri belge sınıfınızın üye değişkenleri olarak uygulayın. Örneğin, karalama program türünün veri üyesi bildirir `CObList` — işaretçileri depolar bağlı bir liste `CObject` nesneleri. Bu liste, serbest çizim noktalar dizileri depolamak için kullanılır.

Belgenizin üye verileri nasıl uygulayacağınıza uygulamanızın doğası hakkında bağlıdır. Çıkış yardımcı olmak için bir grup "koleksiyon sınıflarının" MFC sağlar — diziler, listeler ve eşlemeler (sözlük), C++ şablonları temel alan koleksiyonlar da dahil olmak üzere — çeşitli ortak veri türleri gibi yalıtan sınıflar birlikte `CString`, `CRect`, `CPoint`, `CSize`, ve `CTime`. Bu sınıflar hakkında daha fazla bilgi için bkz. [sınıf kitaplığına genel bakış](../mfc/class-library-overview.md) içinde *MFC başvurusu*.

Belgenizin üye veri tanımladığınızda, ayarlayın ve veri öğelerini alın ve bunları kullanışlı diğer işlemleri gerçekleştirmek için belge sınıfa üye işlevleri genellikle ekleyeceksiniz.

Kendi görünümlerinizi görünümün oluşturma zamanında yüklenen belge, görünüm işaretçisi kullanılarak belge nesnesi erişin. Bu işaretçiyi bir görünümün üye işlevlerini çağırarak alabilirsiniz `CView` üye işlevi `GetDocument`. Bu belge türü kendi işaretçiye emin olun. Daha sonra işaretçiyle public belge üyeleri erişebilir.

Sık kullanılan veri aktarımı doğrudan erişim gerektiren ya da belge sınıfının ortak olmayan üyeler kullanmak istediğiniz belge sınıfı (C++ koşullarında) bir arkadaş sınıf görünümü yapmak isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)

