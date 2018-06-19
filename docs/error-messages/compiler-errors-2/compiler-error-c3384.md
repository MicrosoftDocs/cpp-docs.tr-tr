---
title: Derleyici Hatası C3384 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3384
dev_langs:
- C++
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab09df08edb9f1d5808f2214535c76b20fda62b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251412"
---
# <a name="compiler-error-c3384"></a>Derleyici Hatası C3384
'type_parameter': değer kısıtlaması ile ref karşılıklı olarak birbirini dışlar  
  
 Her ikisi için genel bir tür sınırlamak olamaz `value class` ve `ref class`.  
  
 Bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3384 oluşturur.  
  
```  
// C3384.cpp  
// compile with: /c /clr  
generic <typename T>  
where T : ref class  
where T : value class   // C3384  
ref class List {};  
```