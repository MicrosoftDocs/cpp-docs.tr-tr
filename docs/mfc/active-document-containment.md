---
title: Etkin Belge Kapsaması
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- MFC, COM support
- active document containers [MFC], about active document containers
- MFC COM, active document containment
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
ms.openlocfilehash: dc13384454c4732d3efbf99def5d05dd4f2d44aa
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776576"
---
# <a name="active-document-containment"></a>Etkin Belge Kapsaması

Etkin belge kapsaması oluşturmanızı ve her bir belge türü için birden çok uygulama çerçeveleri kullanın zorlamak yerine belgelerle çalışmak üzere tek bir çerçevesinde sağlayan bir teknolojidir. OLE yalnızca tek bir içeriğin etkin olabilir, bileşik bir belgeye katıştırılmış nesneleri ile çalışır, temel OLE teknolojisini farklıdır. Etkin belge kapsaması ile tek bir çerçeve bağlamında tüm belgeyi (ilişkili menüler, araç çubukları ve benzeri dahil olmak üzere diğer bir deyişle, tüm uygulamanın) etkinleştirin.

Etkin belge kapsama teknolojinin Office Binder uygulamak için Microsoft Office ilk olarak geliştirilmiştir. Ancak, teknolojinin Office Binder dışında etkin belge kapsayıcıları desteklemek için esnek ve belge sunucuları Office ve Office ile uyumlu uygulamaların dışında destekleyebilir.

Etkin belgeler barındıran uygulaması olarak adlandırılan bir [etkin belge kapsayıcı](../mfc/active-document-containers.md). Microsoft Office Binder ya da Microsoft Internet Explorer gibi kapsayıcılar örnekleridir.

Etkin belge kapsaması OLE uzantıları kümesi belgeler gibi OLE bileşik belge teknolojinin uygulanır. Katıştırılmış içeriği tek bir parçasını yerine tüm belgeyi temsil etmek eklenebilir, yerinde bir nesne sağlayan ek arabirimleri uzantılarıdır. OLE belgeleri olarak, etkin belge kapsaması etkin belgeler ve kullanıcı arabirimi ve düzenleme özellikleri etkin belgeler için kendilerini sağlayan sunucular için görünen alanın sağlayan kapsayıcı kullanır.

Bir [etkin belge sunucusu](../mfc/active-document-servers.md) burada nesne içinde etkinleştirilmesi izin uzantı arabirimlerini destekler her nesne bir veya daha fazla etkin belge sınıfları destekleyen bir uygulama (örneğin, Word, Excel veya PowerPoint) olan bir uygun kapsayıcı.

Bir [etkin belgeyi](../mfc/active-documents.md) (Word veya Excel gibi bir etkin belgeyi sunucusundan sağlanır), başka bir etkin belge kapsayıcı içindeki bir nesne olarak katıştırılır temelde tam ölçekli, geleneksel belgedir. Katıştırılmış nesneler aksine etkin belgeler, sayfalar üzerinde tam denetime sahip ve tam arabirimi uygulama (ile tüm temel alınan komutlar ve araçlar), bunları düzenlemek için kullanıcı tarafından kullanılabilir.

Etkin belge standart bir OLE katıştırılmış nesne ayrım tarafından en iyi anlaşılmalıdır. OLE kural, bir nesnenin sahip olduğu belge sayfasında görüntülenen biridir ve belge bir OLE kapsayıcı tarafından yönetilir. Kapsayıcı belgenin geri kalanında katıştırılmış nesnenin verilerle depolar. Ancak, katıştırılmış nesneler üzerinde göründükleri sayfasını kontrol etmez, sınırlıdır.

Etkin belge kapsayıcı uygulaması, kullanıcılar, etkin belgeler (Office Binder bölümlerde olarak adlandırılır) oluşturabilir, sık kullandığınız uygulamalar (Bu uygulamalar etkin belgeyi etkin olması koşuluyla) kullanarak, kullanıcılar sonuç projesi olarak yönetebilir henüz bir Yazdırılan vb. benzersiz olarak adlandırılmış tek bir varlık kaydedildi. Aynı şekilde, bir kullanıcı bir Internet tarayıcısı, yerel dosya sistemleri yanı sıra tüm ağ ile tek bir konumdan depolama belgelere göz atabilmenizi bir tek belge depolama varlık olarak davranabilirsiniz.

## <a name="sample-programs"></a>Örnek program

- [MFCBIND](../overview/visual-cpp-samples.md) örnek etkin belge kapsayıcı uygulaması uygulanışı gösterilmektedir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC COM](../mfc/mfc-com.md)
