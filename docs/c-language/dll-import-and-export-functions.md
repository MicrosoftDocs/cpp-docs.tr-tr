---
title: "DLL içeri ve dışarı aktarma işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], importing
- dllimport attribute [C++], storage-class attribute
- DLL exports [C++]
- declaring functions, with dllexport and dllimport
- extended storage-class attributes
- dllexport attribute [C++], storage-class attribute
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b79856a524cb9693d43d9929b22d6c63db5ba319
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dll-import-and-export-functions"></a>DLL İçeri ve Dışarı Aktarma İşlevleri
**Microsoft özel**  
  
 Bu konu hakkında en eksiksiz ve güncel bilgi bulunabilir [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
 **Dllimport** ve `dllexport` depolama sınıfı değiştiricileri olan C dil için Microsoft'a özgü uzantılar. Bu değiştiriciler, DLL arabirimini istemciye (yürütülebilir dosya veya başka bir DLL) açık olarak tanımlar. İşlevlerin `dllexport` olarak bildirilmesi, modül tanım (.DEF) dosyasına yönelik gereksinimi ortadan kaldırır. Aynı zamanda **dllimport** ve `dllexport` değiştiricileri veri ve nesneleri ile.  
  
 **Dllimport** ve `dllexport` genişletilmiş öznitelik sözdizimi anahtar sözcüğü ile depolama sınıfı değiştiricileri kullanılan `__declspec`, bu örnekte gösterildiği gibi:  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllExport int j;  
DllExport int n;  
```  
  
 Genişletilmiş depolama sınıfı değiştiricileri sözdizimi hakkında ayrıntılı bilgi için bkz: [genişletilmiş depolama sınıfı öznitelikler](../c-language/c-extended-storage-class-attributes.md).  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C İşlev Tanımları](../c-language/c-function-definitions.md)