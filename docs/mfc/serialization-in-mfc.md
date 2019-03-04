---
title: MFC'de Seri Hale Getirme
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: 5c7dec140635b6d83bdae936d1bb0cef144f825b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262148"
---
# <a name="serialization-in-mfc"></a>MFC'de Seri Hale Getirme

Bu makalede, Microsoft Foundation Class Kitaplığı (nesneler arasında devam etmesine izin vermek için MFC) sağlanan serileştirme mekanizmalarını programınızın çalıştırmaları açıklanmaktadır.

Seri hale getirme için veya bir nesneyi okuma veya yazma disk dosyası gibi bir kalıcı depolama ortamı'ndan işlemidir. Seri hale getirme, burada sırasında veya sonrasında bir programın yürütülmesini yapılandırılmış veriler (örneğin, C++ sınıflarını veya yapılarını) durumunu korumak için istendiğini durumlar için idealdir. MFC tarafından sağlanan serileştirme nesneleri kullanarak, bu dosya işlemleri el ile gerçekleştirmek için gereken kullanıcı oluşturma standart ve tutarlı bir şekilde gerçekleşmesini sağlar.

MFC sınıf serileştirme için yerleşik destek sağlayan `CObject`. Bu nedenle, tüm türetilmiş sınıflar `CObject` yararlanabilirsiniz `CObject`'s serileştirme protokolü.

Temel serileştirme bir nesneyi genellikle kalıcı depolama için üye değişkenlerini değeri tarafından belirtilen geçerli durumuna yazabiliyor olmalıdır olur. Daha sonra nesne tarafından nesnenin durumu depodan okunarak veya serisi kaldırılarak yeniden oluşturulabilir. Serileştirme nesne işaretçileri ve döngüsel başvurular olduğunda bir nesneyi serileştirmek için kullanılan nesneleri tüm ayrıntılarını işler. Önemli nokta, nesnenin kendisini kendi durumunu yazma ve okuma için sorumlu olmasıdır. Bu nedenle, seri hale getirilebilir bir sınıf için temel serileştirme işlemleri uygulamalıdır. Makale serileştirme grubunda gösterildiği gibi bu işlevi bir sınıfa eklemek kolaydır.

MFC kullanan bir nesnenin `CArchive` serileştirilecek nesnenin ve depolama ortamı arasında bir aracı olarak sınıf. Bu nesne her zaman ile ilişkili bir `CFile` seri hale getirme, dosya adı dahil olmak üzere gerekli bilgileri alır ve istenen işlem bir okuma veya yazma olup bir nesne. Bir seri hale getirme işlemi gerçekleştiren nesne kullanabilirsiniz `CArchive` depolama ortamı yapısını bakılmaksızın nesne.

A `CArchive` nesnesini kullanan aşırı yüklenmiş ekleme (**<\<**) ve ayıklama (**>>**) yazma ve okuma işlemlerini gerçekleştirmek için işleçler. Daha fazla bilgi için [depolama ve Arşiv yükleniyor Cobject'leri](../mfc/storing-and-loading-cobjects-via-an-archive.md) serileştirme makalede: Bir nesneyi seri hale getirme.

> [!NOTE]
>  Karıştırmayın `CArchive` sınıfı için olan genel amaçlı iostream sınıfları ile biçimlendirilmiş yalnızca metin. `CArchive` İkili biçime serileştirilmiş nesneler için bir sınıftır.

İsterseniz, kendi mekanizması kalıcı veri depolama için oluşturmak için MFC serileştirme devre dışı bırakabilir. Kullanıcının komut serileştirme başlatmak sınıf üyesi işlevleri geçersiz kılma gerekecektir. İçindeki tartışmalara bakın [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md) ıd_fıle_open ıd_fıle_save ve ıd_fıle_save_as standart komut.

Aşağıdaki makaleler, seri hale getirmek için gereken iki ana görevleri kapsar:

- [Seri hale getirme: Seri hale getirilebilir bir sınıf yapma](../mfc/serialization-making-a-serializable-class.md)

- [Seri hale getirme: Bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)

Makaleyi [seri hale getirme: Serileştirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md) serileştirme uygun bir giriş/çıkış teknik veritabanı uygulamalarında olduğunda açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CArchive Sınıfı](../mfc/reference/carchive-class.md)<br/>
[CObject Sınıfı](../mfc/reference/cobject-class.md)<br/>
[CDocument Sınıfı](../mfc/reference/cdocument-class.md)<br/>
[CFile Sınıfı](../mfc/reference/cfile-class.md)
