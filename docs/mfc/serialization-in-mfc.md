---
title: MFC'de seri hale getirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ebd11488f0f86123bcf95d210072cc61dcc31c60
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409239"
---
# <a name="serialization-in-mfc"></a>MFC'de Seri Hale Getirme

Bu makalede, Microsoft Foundation Class Kitaplığı (nesneler arasında devam etmesine izin vermek için MFC) sağlanan serileştirme mekanizmalarını programınızın çalıştırmaları açıklanmaktadır.

Seri hale getirme için veya bir nesneyi okuma veya yazma disk dosyası gibi bir kalıcı depolama ortamı'ndan işlemidir. Seri hale getirme, burada sırasında veya sonrasında bir programın yürütülmesini yapılandırılmış veriler (örneğin, C++ sınıflarını veya yapılarını) durumunu korumak için istendiğini durumlar için idealdir. MFC tarafından sağlanan serileştirme nesneleri kullanarak, bu dosya işlemleri el ile gerçekleştirmek için gereken kullanıcı oluşturma standart ve tutarlı bir şekilde gerçekleşmesini sağlar.

MFC sınıf serileştirme için yerleşik destek sağlayan `CObject`. Bu nedenle, tüm türetilmiş sınıflar `CObject` yararlanabilirsiniz `CObject`'s serileştirme protokolü.

Temel serileştirme bir nesneyi genellikle kalıcı depolama için üye değişkenlerini değeri tarafından belirtilen geçerli durumuna yazabiliyor olmalıdır olur. Daha sonra nesne tarafından nesnenin durumu depodan okunarak veya serisi kaldırılarak yeniden oluşturulabilir. Serileştirme nesne işaretçileri ve döngüsel başvurular olduğunda bir nesneyi serileştirmek için kullanılan nesneleri tüm ayrıntılarını işler. Önemli nokta, nesnenin kendisini kendi durumunu yazma ve okuma için sorumlu olmasıdır. Bu nedenle, seri hale getirilebilir bir sınıf için temel serileştirme işlemleri uygulamalıdır. Makale serileştirme grubunda gösterildiği gibi bu işlevi bir sınıfa eklemek kolaydır.

MFC kullanan bir nesnenin `CArchive` serileştirilecek nesnenin ve depolama ortamı arasında bir aracı olarak sınıf. Bu nesne her zaman ile ilişkili bir `CFile` seri hale getirme, dosya adı dahil olmak üzere gerekli bilgileri alır ve istenen işlem bir okuma veya yazma olup bir nesne. Bir seri hale getirme işlemi gerçekleştiren nesne kullanabilirsiniz `CArchive` depolama ortamı yapısını bakılmaksızın nesne.

A `CArchive` nesnesini kullanan aşırı yüklenmiş ekleme (**<\<**) ve ayıklama (**>>**) yazma ve okuma işlemlerini gerçekleştirmek için işleçler. Daha fazla bilgi için bkz. [depolama ve Arşiv yükleniyor Cobject'leri](../mfc/storing-and-loading-cobjects-via-an-archive.md) makalede seri hale getirme: bir nesneyi seri hale getirme.

> [!NOTE]
>  Karıştırmayın `CArchive` sınıfı için olan genel amaçlı iostream sınıfları ile biçimlendirilmiş yalnızca metin. `CArchive` İkili biçime serileştirilmiş nesneler için bir sınıftır.

İsterseniz, kendi mekanizması kalıcı veri depolama için oluşturmak için MFC serileştirme devre dışı bırakabilir. Kullanıcının komut serileştirme başlatmak sınıf üyesi işlevleri geçersiz kılma gerekecektir. İçindeki tartışmalara bakın [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md) ıd_fıle_open ıd_fıle_save ve ıd_fıle_save_as standart komut.

Aşağıdaki makaleler, seri hale getirmek için gereken iki ana görevleri kapsar:

- [Seri hale getirme: Seri Hale Getirilebilir Bir Sınıf Yapma](../mfc/serialization-making-a-serializable-class.md)

- [Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

Makaleyi [seri hale getirme: seri hale getirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md) serileştirme uygun bir giriş/çıkış teknik veritabanı uygulamalarında olduğunda açıklar.

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CArchive Sınıfı](../mfc/reference/carchive-class.md)<br/>
[CObject Sınıfı](../mfc/reference/cobject-class.md)<br/>
[CDocument Sınıfı](../mfc/reference/cdocument-class.md)<br/>
[CFile Sınıfı](../mfc/reference/cfile-class.md)
