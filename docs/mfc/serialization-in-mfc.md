---
description: "Daha fazla bilgi edinin: MFC 'de serileştirme"
title: MFC'de Seri Hale Getirme
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: 278de59c6e091fd59826622553f50503b12602bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217581"
---
# <a name="serialization-in-mfc"></a>MFC'de Seri Hale Getirme

Bu makalede, nesneleri programınızın çalıştırmaları arasında kalıcı hale getirmek için Microsoft Foundation Class Kitaplığı (MFC) içinde sunulan serileştirme mekanizması açıklanmaktadır.

Serileştirme, disk dosyası gibi kalıcı bir depolama ortamına veya bir nesneyi yazma veya okuma işlemidir. Serileştirme, bir programın yürütülmesi sırasında veya sonrasında yapılandırılmış verilerin (C++ sınıfları veya yapıları gibi) durumunu korumak için istendiği durumlarda idealdir. MFC tarafından sunulan serileştirme nesnelerinin kullanılması, bu işlemin standart ve tutarlı bir şekilde oluşmasını sağlar ve bu sayede, kullanıcının el ile dosya işlemleri gerçekleştirme gereksinimini ortadan kaldırmak için bu,

MFC, sınıfında serileştirme için yerleşik destek sağlar `CObject` . Bu nedenle, öğesinden türetilmiş tüm sınıflar `CObject` `CObject` serileştirme protokolünden yararlanabilir.

Serileştirme temel fikri, bir nesnenin, genellikle üye değişkenlerinin değeri ile belirtilen geçerli durumunu kalıcı depolamaya yazabilmesi gerektiği durumdur. Daha sonra nesne, nesneden nesnenin durumu okunurken veya seri durumdan çıkarılırken yeniden oluşturulabilir. Serileştirme, nesne işaretçilerinin tüm ayrıntılarını ve bir nesneyi seri hale getirçalışırken kullanılan nesnelere döngüsel başvuruları işler. Bir anahtar noktası, nesnenin kendisinin kendi durumunu okumaktan ve yazmasından sorumludur. Bu nedenle, bir sınıfın seri hale getirilebilir olması için temel serileştirme işlemlerini uygulaması gerekir. Makalelerin serileştirme grubunda gösterildiği gibi, bu işlevselliği bir sınıfa eklemek kolaydır.

MFC, `CArchive` seri hale getirilecek nesne ve depolama ortamı arasında bir aracı olarak sınıfının bir nesnesini kullanır. Bu nesne her zaman, `CFile` dosya adı ve istenen işlemin bir okuma veya yazma gibi, serileştirme için gerekli bilgileri aldığı bir nesneyle ilişkilendirilir. Serileştirme işlemini gerçekleştiren nesne, `CArchive` depolama ortamının doğası olmadan nesneyi kullanabilir.

Bir `CArchive` nesne **<\<**) and extraction (**>>** , yazma ve okuma işlemlerini gerçekleştirmek için aşırı yüklenmiş ekleme () işleçlerini kullanır. Daha fazla bilgi için, bkz. bir nesneyi seri hale getirme: bir nesneyi serileştirme [ve yükleme](../mfc/storing-and-loading-cobjects-via-an-archive.md) .

> [!NOTE]
> `CArchive`Sınıfı, yalnızca biçimlendirilen metin için olan genel amaçlı ıostream sınıflarıyla karıştırmayın. `CArchive`Sınıfı ikili biçimli serileştirilmiş nesneler içindir.

İsterseniz, kalıcı veri depolama için kendi mekanizmanızı oluşturmak üzere MFC serileştirmesini atlayabilirsiniz. Kullanıcı komutunda serileştirme başlatan sınıf üye işlevlerini geçersiz kılmanız gerekir. ID_FILE_OPEN, ID_FILE_SAVE ve ID_FILE_SAVE_AS standart komutlarının [Teknik notunda](../mfc/tn022-standard-commands-implementation.md) bulunan tartışmaya bakın.

Aşağıdaki makaleler serileştirme için gereken iki ana görevi kapsar:

- [Serileştirme: seri hale getirilebilir bir sınıf oluşturma](../mfc/serialization-making-a-serializable-class.md)

- [Serileştirme: bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)

Seri hale getirme [: serileştirme ve veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md) , serileştirme, veritabanı uygulamalarında uygun bir giriş/çıkış tekniğidir.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../mfc/mfc-concepts.md)<br/>
[Genel MFC konuları](../mfc/general-mfc-topics.md)<br/>
[CArchive sınıfı](../mfc/reference/carchive-class.md)<br/>
[CObject sınıfı](../mfc/reference/cobject-class.md)<br/>
[CDocument sınıfı](../mfc/reference/cdocument-class.md)<br/>
[CFile sınıfı](../mfc/reference/cfile-class.md)
