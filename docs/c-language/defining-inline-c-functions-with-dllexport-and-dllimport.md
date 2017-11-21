---
title: "Dllexport ve dllimport ile satır için C işlevlerini tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline functions [C++], with dllexport and dllimport
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
- dllexport attribute [C++]
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 77776e174b797bd323aff0a77a2f914b8ac0b0ff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>dllexport ve dllimport ile Satır İçin C İşlevlerini Tanımlama
**Microsoft özel**  
  
 `dllexport` özniteliğiyle bir işlevi satır içi olarak tanımlayabilirsiniz. Bu durumda, programdaki herhangi bir modülün işleve başvurup başvurmadığına bakılmaksızın işlevin her zaman örneği oluşturulur ve işlev dışarı aktarılır. İşlevin, başka bir program tarafından içeri aktarıldığı varsayılır.  
  
 Satır içi olarak ile bildirilen bir işlev tanımlayabilirsiniz **dllimport** özniteliği. Bu durumda, işlev (/Ob (satır içi) derleyici seçeneği belirtimi tabi) genişletilmiş ancak hiçbir zaman örneği. Özellikle, satır içi içeri aktarılan bir işlevin adresi alınırsa, DLL'de yer alan işlevin adresi döndürülür. Bu davranış, satır içi olmayan içeri aktarılmış bir işlevin adresini almakla aynıdır.  
  
 Tek bir program (diğer bir deyişle, yürütülebilir bir dosyanın DLL arabirimi olmadan) içinde yaptıkları gibi statik yerel veri ve satır içi işlevler dizelerde DLL ve istemci arasında aynı kimlikleri bakımını yapar.  
  
 İçeri aktarılan satır içi işlevleri sağlarken dikkatli olun. Örneğin, DLL'yi güncelleştirirseniz, istemcinin değiştirilmiş DLL sürümünü kullanacağını varsaymayın. DLL'nin doğru sürümünü yüklediğinizden emin olmak için DLL'nin istemcisini de yeniden oluşturun.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL içeri ve dışarı aktarma işlevleri](../c-language/dll-import-and-export-functions.md)