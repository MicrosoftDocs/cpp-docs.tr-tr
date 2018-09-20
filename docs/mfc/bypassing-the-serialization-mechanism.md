---
title: Seri hale getirme mekanizmasını atlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25fc281e35fc07151fa609d07be540430a6a1da6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399824"
---
# <a name="bypassing-the-serialization-mechanism"></a>Seri Hale Getirme Mekanizmasını Atlama

Gördüğünüz gibi framework okuyup dosyaları gelen ve giden veri yazmak için varsayılan bir yol sağlar. Bir arşiv nesneyi seri hale getirme, harika bir birçok uygulama gereksinimlerine uygun. Bu tür bir uygulama tamamen belleğe bir dosyayı okur, dosyayı güncelleştirmek izin verir ve ardından güncelleştirilmiş sürümü tekrar diske yazar.

Ancak, bazı uygulamaları çok farklı veriler üzerinde işlem yaparsınız ve bu uygulamalar için serileştirme bir arşiv üzerinden uygun değil. Veritabanı programları, yalnızca büyük dosyaları bölümlerini düzenleme programları, yalnızca metin dosyaları yazma programları ve veri dosyalarını paylaşan programları verilebilir.

Bu gibi durumlarda, geçersiz kılabilirsiniz [serileştirme](../mfc/reference/cobject-class.md#serialize) dosyası eylemleri aracılığıyla aktarmak için farklı bir şekilde işlevi bir [CFile](../mfc/reference/cfile-class.md) nesne yerine [CArchive](../mfc/reference/carchive-class.md) nesne.

Kullanabileceğiniz `Open`, `Read`, `Write`, `Close`, ve `Seek` sınıfın üye işlevleri `CFile` bir dosyayı açmaya dosya işaretçiyi (Ara) dosyasında, belirli bir noktaya (bir belirtilen sayıda baytı bir kaydı okuma ) Bu noktada, kullanıcının kaydı güncelleştirmek daha sonra aynı noktaya tekrar arama ve kaydın geri dosyaya yazmak olanak tanır. Framework sizin için dosyayı açar ve kullanabileceğiniz `GetFile` sınıfının üye işlevinde `CArchive` bir işaretçi alma için `CFile` nesne. Daha da karmaşık ve esnek kullanım için geçersiz kılabilirsiniz [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) ve [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) sınıfın üye işlevleri `CWinApp`. Daha fazla bilgi için bkz. [CFile](../mfc/reference/cfile-class.md) içinde *MFC başvurusu*.

Bu senaryoda, `Serialize` geçersiz kılma hiçbir şey yapmaz, örneğin, okuma ve yazma belge kapandığında güncel tutmak için bir dosya üstbilgisi istediğiniz sürece.

## <a name="see-also"></a>Ayrıca Bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)

