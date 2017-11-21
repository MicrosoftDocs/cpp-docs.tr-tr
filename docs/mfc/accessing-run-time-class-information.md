---
title: "Çalışma zamanı sınıf bilgilerine erişme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5cdc520118c0d50590927a88de816a593ea5e146
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="accessing-run-time-class-information"></a>Çalışma Süresi Sınıf Bilgilerine Erişme
Bu makalede, çalışma zamanında bir nesne sınıfının hakkındaki bilgilere erişmek açıklanmaktadır.  
  
> [!NOTE]
>  MFC kullanmayan [çalışma zamanı türü bilgileri](../cpp/run-time-type-information.md) Visual C++ 4.0 sunulan (RTTI) desteği.  
  
 Sınıfından türetilen durumunda [CObject](../mfc/reference/cobject-class.md) ve kullanılan **DECLARE**_**dinamik** ve `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE`, veya `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları makalesinde açıklanan [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md), `CObject` sınıfının kesin bir nesne sınıfının çalışma zamanında belirleme olanağı vardır.  
  
 Bu yetenek, ek tür işlev bağımsız değişkenleri denetlemesi gerektiğinde ve bir nesne sınıfına göre özel amaçlı kodu yazarken gerekir en yararlı olur. Sanal işlevler işlevselliğini çoğaltır ancak, bu yöntem genellikle önerilmez.  
  
 `CObject` Üye işlevi `IsKindOf` belirli bir nesne için belirli bir sınıf aitse veya belirli bir sınıftan türetildiği durumda olduğu belirlemek için kullanılabilir. Bağımsız değişkeni `IsKindOf` olan bir `CRuntimeClass` kullanarak elde nesne `RUNTIME_CLASS` makrosu sınıfı adı.  
  
### <a name="to-use-the-runtimeclass-macro"></a>RUNTIME_CLASS makrosu kullanmak için  
  
1.  Kullanım `RUNTIME_CLASS` sınıfı için aşağıda gösterildiği gibi sınıfın adı ile `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]  
  
 Nadiren çalışma zamanı sınıf nesnesi doğrudan erişmek gerekir. Çalışma zamanı sınıf nesnesine geçirmek için daha yaygın bir kullanımdır `IsKindOf` sonraki yordamda gösterildiği gibi işlev. `IsKindOf` İşlevi bir nesne için belirli bir sınıfın ait olup olmadığını görmek için sınar.  
  
#### <a name="to-use-the-iskindof-function"></a>Iskindof işlevi kullanmak için  
  
1.  Çalışma zamanı sınıf desteği sınıfı olduğundan emin olun. Diğer bir deyişle, doğrudan veya dolaylı olarak öğesinden türetilmiş sınıf gerekir `CObject` ve kullanılan **DECLARE**_**dinamik** ve `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE`, veya `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları makalesinde açıklanan [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md).  
  
2.  Çağrı `IsKindOf` bu sınıfındaki nesneler için üye işlevi kullanarak `RUNTIME_CLASS` oluşturmak için makrosu `CRuntimeClass` bağımsız değişkeni, aşağıda gösterildiği gibi:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]  
  
     [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]  
  
    > [!NOTE]
    >  Iskindof döndürür **TRUE** nesne belirtilen sınıf veya belirtilen sınıfından türetilmiş bir sınıf üyesi ise. `IsKindOf`Gerekirse, türetilen Microsoft Foundation sınıflar için birden çok devralma kullanabilmenize karşın, birden çok devralma veya sanal taban sınıflar desteklemez.  
  
 Bir çalışma zamanı sınıf bilgileri nesneleri dinamik oluşturulmasında kullanılır. Bu işlem makalesinde açıklanan [dinamik Nesne oluşturma](../mfc/dynamic-object-creation.md).  
  
 Daha ayrıntılı seri hale getirme hakkında bilgi ve çalışma zamanı sınıf bilgileri için makalelerine bakın [MFC'deki dosyalar](../mfc/files-in-mfc.md) ve [seri hale getirme](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject kullanma](../mfc/using-cobject.md)

