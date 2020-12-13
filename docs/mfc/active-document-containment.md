---
description: 'Hakkında daha fazla bilgi edinin: etkin belge kapsama'
title: Etkin Belge Kapsaması
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- MFC, COM support
- active document containers [MFC], about active document containers
- MFC COM, active document containment
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
ms.openlocfilehash: 9a190e0203152e2411699aa601a095a530303546
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150390"
---
# <a name="active-document-containment"></a>Etkin Belge Kapsaması

Etkin belge kapsama, her belge türü için birden çok uygulama çerçevesi oluşturup kullanmanıza zorlamak yerine belgelerle çalışmak üzere tek bir çerçeve sağlayan bir teknolojidir. Bu, OLE içindeki temel OLE teknolojisinden farklıdır. Bu, tek bir içerik parçasının etkin olduğu bileşik bir belge içindeki katıştırılmış nesneler ile çalışmaktadır. Etkin belge kapsamadan, tek bir çerçeve bağlamında tüm belgeyi (diğer bir deyişle, ilişkili menüler, araç çubukları vb. dahil olmak üzere tüm bir uygulama) etkinleştirirsiniz.

Etkin belge kapsama teknolojisi, başlangıçta Office Ciltçi uygulaması Microsoft Office için geliştirilmiştir. Ancak, teknoloji Office Ciltçi dışındaki etkin belge kapsayıcılarını desteklemeye yetecek kadar esnektir ve Office ve Office uyumlu uygulamalar dışındaki belge sunucularını destekleyebilir.

Etkin belgeleri barındıran uygulamaya [etkin bir belge kapsayıcısı](active-document-containers.md)denir. Bu kapsayıcıların örnekleri Microsoft Office Ciltçi veya Microsoft Internet Explorer.

Etkin belge kapsama, OLE belgelerine bir uzantılar kümesi olarak uygulanır ve OLE belgelerinin bileşik belge teknolojisidir. Uzantılar, bir eklenebilir, yerinde nesnenin tek bir katıştırılmış içerik parçası yerine tüm belgeyi temsil etmesini sağlayan ek arayüzlerdir. OLE belgelerinde olduğu gibi, etkin belge kapsamı etkin belgeler için görüntüleme alanı ve etkin belgelerin kendileri için de Kullanıcı arabirimi ve işleme özellikleri sağlayan bir kapsayıcı kullanır.

[Etkin bir belge sunucusu](active-document-servers.md) , bir veya daha fazla etkin belge sınıfını destekleyen bir uygulama (Word, Excel veya PowerPoint gibi), her nesnenin kendisi nesnenin uygun bir kapsayıcıda etkinleştirilmesini sağlayan uzantı arabirimlerini desteklediği bir uygulamadır.

[Etkin bir belge](active-documents.md) (Word veya Excel gibi etkin bir belge sunucusundan sağlanır), aslında başka bir etkin belge kapsayıcısı içindeki bir nesne olarak katıştırılmış olan tam ölçekli, geleneksel bir belgedir. Katıştırılmış nesnelerden farklı olarak, etkin belgeler kendi sayfaları üzerinde tam denetime sahiptir ve uygulamanın tam arabirimine sahip olur (tüm alt komutları ve araçları ile birlikte) Kullanıcı tarafından düzenleme için kullanılabilir.

Etkin bir belge, standart OLE Embedded nesnesinden ayırt edici en iyi şekilde anlaşılır. OLE kuralına göre, gömülü bir nesne, kendisine ait olan belge sayfasında görüntülenen bir belgedir ve belge bir OLE kapsayıcısı tarafından yönetilir. Kapsayıcı, katıştırılmış nesnenin verilerini belgenin geri kalanı ile depolar. Ancak, katıştırılmış nesneler göründükleri sayfayı denetolmadıklarından sınırlı olur.

Etkin bir belge kapsayıcısı uygulamasının kullanıcıları, sık kullanılan uygulamalarını (Bu uygulamalar etkin belge etkindir) kullanarak, etkin belgeler (Office Ciltçi 'de bölümler olarak adlandırılır) oluşturabilir, ancak kullanıcılar, sonuçta elde edilen projeyi tek bir varlık olarak yönetebilir, bu da benzersiz şekilde adlandırılmış, kaydedilmiş, yazdırılabilir, vb. olabilir. Aynı şekilde, bir Internet tarayıcısının bir kullanıcısı, tüm ağı ve yerel dosya sistemlerini tek bir konumdan tek bir konumdan, bu depolama alanındaki belgelere gözatmanıza olanak tanıyan tek bir belge depolama varlığı olarak ele alabilir.

## <a name="sample-programs"></a>Örnek programlar

- [Mfcbind](../overview/visual-cpp-samples.md) örneği etkin bir belge kapsayıcısı uygulamasının uygulamasını gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC COM](mfc-com.md)
