---
title: Depolama ve bir arşiv kullanarak Cobject'leri yükleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a2dc227815f8888b85784ea92e58b3e91ffc83a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954981"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Bir Arşiv Kullanarak CObject'leri Depolama ve Yükleme
Depolama ve yükleme `CObject`s bir arşiv aracılığıyla ek göz önünde bulundurarak gerektirir. Bazı durumlarda, çağırmalısınız `Serialize` nesnesinin işlevi burada `CArchive` nesnesidir bir parametresi `Serialize` kullanarak aksine, çağrısı **< \<** veya **>>** işleci `CArchive`. Dikkate alınması gereken önemli olgu olan `CArchive` **>>** işleci yapıları `CObject` göre bellekte `CRuntimeClass` bilgileri önceden tarafından depolanmasını arşiv dosyasına yazılır.  
  
 Kullanıp bu nedenle, `CArchive` **< \<** ve **>>** arama karşı işleçleri `Serialize`, bağlıdır, *gerek* Arşiv yüklenirken dinamik olarak nesne yeniden oluşturmak için temel alarak önceden depolanan `CRuntimeClass` bilgi. Kullanım `Serialize` işlevi aşağıdaki durumlarda:  
  
-   Nesne seri durumdan çıkarılırken, nesnenin tam sınıfı önceden biliyor.  
  
-   Nesne seri durumdan çıkarılırken, önceden kendisi için ayrılan bellek yok.  
  
> [!CAUTION]
>  Nesnesini kullanarak yüklerseniz `Serialize` işlevi, nesnesini kullanarak depolamalısınız `Serialize` işlevi. Kullanarak depolamayın `CArchive` **<<** işleci ve sonra Yük kullanma `Serialize` işlev veya kullanılarak `Serialize` işlev ve kullanarak yük `CArchive >>` işleci.  
  
 Aşağıdaki örnek durumlarda gösterilmektedir:  
  
 [!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]  
  
 [!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]  
  
 Seri hale getirilebilir sınıfınız katıştırılmış tanımlıyorsa Özet olarak, `CObject` bir üye olarak gereken *değil* kullanmak `CArchive` **< \<** ve **>>** o nesnenin işleç ancak çağırmalıdır `Serialize` yerine işlev. Ayrıca, seri hale getirilebilir bir sınıf için bir işaretçi tanımlıyorsa bir `CObject` (veya bir nesne türetilmiş `CObject`) üyesi, ancak yapıları bu bir kendi Oluşturucusu nesnesinde de çağırmanız gerekir `Serialize`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

