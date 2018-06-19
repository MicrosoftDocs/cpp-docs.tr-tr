---
title: 'Nasıl yapılır: interior_ptr anahtar sözcüğü ile değer türleri bildirme (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6015d5a61589b8ed2d38b6491392fd42e4f38ef1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879483"
---
# <a name="how-to-declare-value-types-with-the-interiorptr-keyword-ccli"></a>Nasıl yapılır: interior_ptr Anahtar Sözcüğü ile Değer Türleri Bildirme (C++/CLI)
Bir `interior_ptr` değer türü ile kullanılabilir.  
  
> [!IMPORTANT]
>  Bu dil özelliği tarafından desteklenen **/CLR** derleyici seçeneği, ancak tarafından **/ZW** derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki C + +/ CLI örnek nasıl kullanılacağını gösteren bir `interior_ptr` bir değer türü.  
  
### <a name="code"></a>Kod  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Değer türü `this` işaretçi interior_ptr için değerlendirir.  
  
 Değer türü statik olmayan üye-işlevi gövdesinde `V`, `this` ifade türü olan `interior_ptr<V>` değeri işlevi çağrıldığında nesne adresidir.  
  
### <a name="code"></a>Kod  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, statik üyeleriyle address-of işleci kullanmayı gösterir.  
  
 Yerel bir işaretçi bir statik Visual C++ tür üyesi adresini verir.  Değer türü üyesinin çalışma zamanı yığında ayrılmış ve atık toplayıcısı tarafından taşınabilir çünkü statik değer türü üyesinin adresi yönetilen bir işaretçidir.  
  
### <a name="code"></a>Kod  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
22  
23  
hello  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)