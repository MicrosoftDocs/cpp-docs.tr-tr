---
title: NMAKE makrosu kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fc5c6c8851654b1a767967ffc900886d75521130
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-nmake-macro"></a>NMAKE Makrosu Kullanma
Makro kullanmak için bir dolar işareti ($) gibi öncesinde ayraç içine adını alın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
$(macroname)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Boşluk izin verilir. Parantez isteğe bağlıdır, *makroadı* tek bir karakter değil. Tanım dizesi değiştirir $(*makroadı*); bir tanımsız makrosu boş bir dize değiştirilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
 [Makro değiştirme](../build/macro-substitution.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve NMAKE](../build/macros-and-nmake.md)