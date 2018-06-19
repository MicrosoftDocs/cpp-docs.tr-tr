---
title: DLL içeri ve dışarı aktarma işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- dllimport attribute [C++], storage-class attribute
- DLL exports [C++]
- declaring functions, with dllexport and dllimport
- extended storage-class attributes
- dllexport attribute [C++], storage-class attribute
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da456b7caca59fb874f4da87a342162b53c09319
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384960"
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