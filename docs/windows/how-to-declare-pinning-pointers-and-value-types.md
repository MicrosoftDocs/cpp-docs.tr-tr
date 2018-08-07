---
title: 'Nasıl yapılır: sabitleme işaretçileri ve değer türlerini | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- value types, declaring
- pinning pointers
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 57c6ed79f9ecb74533a7ffaf2861af8bee9e257a
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569761"
---
# <a name="how-to-declare-pinning-pointers-and-value-types"></a>Nasıl yapılır: Sabitleme İşaretçileri ve Değer Türlerini Bildirme
Örtük olarak bir değer türü kutulanabilir. Değer türü nesne bir sabitleme işaretçisine kendisi ve kullanım ardından bildirebilirsiniz bir **pin_ptr** kutulanmış değer türü.  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```cpp  
// pin_ptr_value.cpp  
// compile with: /clr  
value struct V {  
   int i;  
};  
  
int main() {  
   V ^ v = gcnew V;   // imnplicit boxing  
   v->i=8;  
   System::Console::WriteLine(v->i);  
   pin_ptr<V> mv = &*v;  
   mv->i = 7;  
   System::Console::WriteLine(v->i);  
   System::Console::WriteLine(mv->i);  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```Output  
8  
7  
7  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)