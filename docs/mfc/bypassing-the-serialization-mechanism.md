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
ms.openlocfilehash: 9252e08fe672f111dcf2b289b1b12891022a318d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931095"
---
# <a name="bypassing-the-serialization-mechanism"></a>Seri Hale Getirme Mekanizmasını Atlama
Görülen çerçevesini okuyup için ve dosyalarından veri yazmak için varsayılan bir yol sağlar. Arşiv nesnesi seri hale getirme harika bir birçok uygulama gereksinimlerine uygun. Bu tür bir uygulama bir dosya tamamen belleğe okur, dosyayı güncelleştirmek kullanıcının izin verir ve ardından yeniden diske güncelleştirilmiş sürüm yazar.  
  
 Ancak, bazı uygulamalar üzerindeki veriler çok farklı çalışır ve bu uygulamalar için serileştirme bir arşiv üzerinden uygun değil. Örnek Veritabanı programları, yalnızca büyük dosyalar bölümlerini düzenleme programları, yalnızca metin dosyaları yazma programları ve veri dosyalarını paylaşan programları içerir.  
  
 Bu durumlarda, geçersiz kılabilirsiniz [serileştirme](../mfc/reference/cobject-class.md#serialize) dosya eylemleri arasında aktarmak için farklı bir şekilde işlevinde bir [CFile](../mfc/reference/cfile-class.md) nesne yerine bir [CArchive](../mfc/reference/carchive-class.md) nesnesi.  
  
 Kullanabileceğiniz `Open`, `Read`, `Write`, `Close`, ve `Seek` sınıfının üye işlevleri `CFile` bir dosyayı açmaya dosya işaretçisini taşımak (Ara) dosyasında, belirli bir noktaya okuma bir kayıt (bir belirtilen bayt sayısı ) Bu noktada, kayıt güncelleştirmesi sonra aynı noktasına yeniden arama ve kaydı geri veya dosyaya yazmak kullanıcının izin verin. Framework sizin için dosyayı açar ve kullanabileceğiniz `GetFile` sınıfının üye işlevini `CArchive` gösteren bir işaretçi almak için `CFile` nesnesi. Daha da karmaşık ve esnek kullanım için kılmanız [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) ve [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) sınıfının üye işlevleri `CWinApp`. Daha fazla bilgi için bkz [CFile](../mfc/reference/cfile-class.md) içinde *MFC başvurusu*.  
  
 Bu senaryoda, `Serialize` geçersiz kılma hiçbir şey yapmaz, örneğin okuma ve yazma belge kapandığında güncel tutmak için bir dosya üstbilgisi istemediğiniz sürece.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri Kullanma](../mfc/using-documents.md)

