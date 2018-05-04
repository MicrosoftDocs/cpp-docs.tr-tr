---
title: NMAKE makrosu kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6bf098a3723aa7b067b8192bf503975998e4e98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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