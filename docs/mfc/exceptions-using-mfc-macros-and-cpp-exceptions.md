---
title: "Özel durumlar: MFC makroları ve C++ özel durumlarını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6597f43deee73addff8e8f2045a38d7b1109fc0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Özel Durumlar: MFC Makroları ve C++ Özel Durumlarını Kullanma
Bu makalede MFC özel durum işleme makroları ve C++ özel durum işleme anahtar sözcükleri kullanan kodu yazmada dikkat edilmesi gerekenler açıklanmaktadır.  
  
 Bu makalede aşağıdaki konuları içerir:  
  
-   [Özel anahtar sözcükleri ve makrolar karıştırma](#_core_mixing_exception_keywords_and_macros)  
  
-   [Try blokları içindeki catch blokları](#_core_try_blocks_inside_catch_blocks)  
  
##  <a name="_core_mixing_exception_keywords_and_macros"></a>Özel anahtar sözcükleri ve makrolar karıştırma  
 MFC özel durum makroları ve C++ özel durum anahtar sözcükleri aynı program karıştırabilirsiniz. Ancak, kapsam dışı olduğunuzda özel durum işleme anahtar sözcükleri kullanarak kod'in almadığı makrolar özel durum nesneleri otomatik olarak silmek için aynı blokta C++ özel durum sözcüklerle MFC makroları karıştıramazsınız. Daha fazla bilgi için bkz: [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Makrolar ve anahtar sözcükler arasındaki temel fark özel kapsam dışına çıktığında makrolar Yakalanan özel durum "otomatik olarak" Sil ' dir. Anahtar sözcükler kullanarak kod yoktur; özel durumlar bir catch bloğu içinde yakalanan açıkça silinmelidir. Makrolar ve C++ özel durum anahtar sözcüklerini karıştırma bir özel durum nesnesi silinmedi bellek sızıntıları neden veya bir özel durum iki kez silindiğinde yığın bozulması.  
  
 Aşağıdaki kod, örneğin, özel durum işaretçinin geçersiz kılar:  
  
 [!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]  
  
 Sorun nedeniyle oluşur `e` yürütme "İç" dışında geçerken silinmiş **CATCH** bloğu. Kullanarak `THROW_LAST` makrosu yerine **THROW** deyimi neden olacak "dış" **CATCH** geçerli bir işaretçi almaya engelle:  
  
 [!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]  
  
##  <a name="_core_try_blocks_inside_catch_blocks"></a>Try blokları içindeki Catch blokları  
 Geçerli özel durumun içinden yeniden atılamıyor bir **deneyin** içinde blok bir **CATCH** bloğu. Aşağıdaki örnekte geçersiz:  
  
 [!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]  
  
 Daha fazla bilgi için bkz: [özel durumlar: özel durum içeriklerini İnceleme](../mfc/exceptions-examining-exception-contents.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

