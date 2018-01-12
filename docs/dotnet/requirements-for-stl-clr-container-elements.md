---
title: "STL/CLR kapsayıcı öğeleri için gereksinimler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3317e3c9349963fc24b37b421def05c475732fd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="requirements-for-stlclr-container-elements"></a>STL/CLR Kapsayıcı Öğeleri için Gereksinimler
STL/CLR kapsayıcıları eklenen tüm başvuru türleri, en azından aşağıdaki öğeleri olması gerekir:  
  
-   Ortak kopya Oluşturucu.  
  
-   Bir ortak atama işleci.  
  
-   Bir ortak yıkıcı.  
  
 Ayrıca, ilişkilendirilebilir kapsayıcıları gibi [ayarlamak](../dotnet/set-stl-clr.md) ve [harita](../dotnet/map-stl-clr.md) olan tanımlanan, bir ortak karşılaştırma işleci olmalıdır `operator<` varsayılan olarak. Bazı işlemler kapsayıcılarında ortak varsayılan bir oluşturucu ve tanımlanması için bir ortak eşdeğer işleci de gerektirebilir.  
  
 Başvuru türleri, değer türleri ve tanıtıcıları gibi başvurmak için ilişkilendirilebilir bir kapsayıcıya eklenecek olan türlerini bir karşılaştırma işleci gibi gerekir `operator<` tanımlanmış. Değer türleri veya türleri başvurmak için tanıtıcıları için ortak kopya Oluşturucu, ortak atama işleci ve bir ortak yıkıcı gereksinimleri yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)