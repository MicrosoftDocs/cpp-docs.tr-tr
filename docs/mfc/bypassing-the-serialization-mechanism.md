---
title: "Seri hale getirme mekanizmasını atlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0beb14c2ddb159616f7cbb34b83b68e84ef0a1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bypassing-the-serialization-mechanism"></a>Seri Hale Getirme Mekanizmasını Atlama
Görülen çerçevesini okuyup için ve dosyalarından veri yazmak için varsayılan bir yol sağlar. Arşiv nesnesi seri hale getirme harika bir birçok uygulama gereksinimlerine uygun. Bu tür bir uygulama bir dosya tamamen belleğe okur, dosyayı güncelleştirmek kullanıcının izin verir ve ardından yeniden diske güncelleştirilmiş sürüm yazar.  
  
 Ancak, bazı uygulamalar üzerindeki veriler çok farklı çalışır ve bu uygulamalar için serileştirme bir arşiv üzerinden uygun değil. Örnek Veritabanı programları, yalnızca büyük dosyalar bölümlerini düzenleme programları, yalnızca metin dosyaları yazma programları ve veri dosyalarını paylaşan programları içerir.  
  
 Bu durumlarda, geçersiz kılabilirsiniz [serileştirme](../mfc/reference/cobject-class.md#serialize) dosya eylemleri arasında aktarmak için farklı bir şekilde işlevinde bir [CFile](../mfc/reference/cfile-class.md) nesne yerine bir [CArchive](../mfc/reference/carchive-class.md) nesnesi.  
  
 Kullanabileceğiniz **açmak**, **okuma**, **yazma**, **Kapat**, ve `Seek` sınıfının üye işlevleri `CFile` bir dosyayı açmak için , dosya işaretçisini (Ara) dosyasında, belirli bir noktaya okuma bir kayıt (bayt belirtilen bir sayısı) Bu noktada, let kullanıcı güncelleştirme kayıt sonra arama yeniden aynı noktası ve kayıt geri dosyaya yazma. Framework sizin için dosyayı açar ve kullanabileceğiniz `GetFile` sınıfının üye işlevini `CArchive` gösteren bir işaretçi almak için `CFile` nesnesi. Daha da karmaşık ve esnek kullanım için kılmanız [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) ve [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) sınıfının üye işlevleri `CWinApp`. Daha fazla bilgi için bkz [CFile](../mfc/reference/cfile-class.md) içinde *MFC başvurusu*.  
  
 Bu senaryoda, `Serialize` geçersiz kılma hiçbir şey yapmaz, örneğin okuma ve yazma belge kapandığında güncel tutmak için bir dosya üstbilgisi istemediğiniz sürece.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri kullanma](../mfc/using-documents.md)

