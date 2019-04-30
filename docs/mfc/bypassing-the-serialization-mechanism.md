---
title: Seri Hale Getirme Mekanizmasını Atlama
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
ms.openlocfilehash: 1937098de30884be327c67a698dbb0023be248bb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345195"
---
# <a name="bypassing-the-serialization-mechanism"></a>Seri Hale Getirme Mekanizmasını Atlama

Gördüğünüz gibi framework okuyup dosyaları gelen ve giden veri yazmak için varsayılan bir yol sağlar. Bir arşiv nesneyi seri hale getirme, harika bir birçok uygulama gereksinimlerine uygun. Bu tür bir uygulama tamamen belleğe bir dosyayı okur, dosyayı güncelleştirmek izin verir ve ardından güncelleştirilmiş sürümü tekrar diske yazar.

Ancak, bazı uygulamaları çok farklı veriler üzerinde işlem yaparsınız ve bu uygulamalar için serileştirme bir arşiv üzerinden uygun değil. Veritabanı programları, yalnızca büyük dosyaları bölümlerini düzenleme programları, yalnızca metin dosyaları yazma programları ve veri dosyalarını paylaşan programları verilebilir.

Bu gibi durumlarda, geçersiz kılabilirsiniz [serileştirme](../mfc/reference/cobject-class.md#serialize) dosyası eylemleri aracılığıyla aktarmak için farklı bir şekilde işlevi bir [CFile](../mfc/reference/cfile-class.md) nesne yerine [CArchive](../mfc/reference/carchive-class.md) nesne.

Kullanabileceğiniz `Open`, `Read`, `Write`, `Close`, ve `Seek` sınıfın üye işlevleri `CFile` bir dosyayı açmaya dosya işaretçiyi (Ara) dosyasında, belirli bir noktaya (bir belirtilen sayıda baytı bir kaydı okuma ) Bu noktada, kullanıcının kaydı güncelleştirmek daha sonra aynı noktaya tekrar arama ve kaydın geri dosyaya yazmak olanak tanır. Framework sizin için dosyayı açar ve kullanabileceğiniz `GetFile` sınıfının üye işlevinde `CArchive` bir işaretçi alma için `CFile` nesne. Daha da karmaşık ve esnek kullanım için geçersiz kılabilirsiniz [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) ve [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) sınıfın üye işlevleri `CWinApp`. Daha fazla bilgi için bkz. [CFile](../mfc/reference/cfile-class.md) içinde *MFC başvurusu*.

Bu senaryoda, `Serialize` geçersiz kılma hiçbir şey yapmaz, örneğin, okuma ve yazma belge kapandığında güncel tutmak için bir dosya üstbilgisi istediğiniz sürece.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)
