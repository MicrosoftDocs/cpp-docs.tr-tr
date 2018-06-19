---
title: Yeni başvuru, gcnew (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9533675d2894b3c3d99e3fb57abded8ea4e99d7a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879067"
---
# <a name="ref-new-gcnew--c-component-extensions"></a>yeni başvuru, gcnew (C++ Bileşen Uzantıları)
`ref new` Birleşik anahtar sözcüğü ayırır nesne erişilemez duruma ve bir işleyici döner toplanacak olan bir türü örneği ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) ayrılmış nesnesine.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 Tarafından ayrılmış bir türünün bir örneği için bellek `ref new` otomatik olarak serbest bırakıldı.  
  
 A `ref new` işlemi atar `OutOfMemoryException` bellek ayıramıyor ise.  
  
 Yerel C++ türleri için bellek tahsis ve serbest hakkında daha fazla bilgi için bkz: [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Kullanım `ref new` ömrü otomatik olarak yönetmek istediğiniz Windows çalışma zamanı nesneler için bellek ayrılamadı. Başvuru sayısı başvuru son kopyasını fazlası kapsam dışında sonra oluşan sıfır gittiğinde nesne otomatik olarak serbest. Daha fazla bilgi için bkz: [Ref sınıflar ve yapılar](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 Tarafından yönetilen türü (başvuru veya değer türü) için bellek tahsis `gcnew`ve atık toplama kullanarak serbest bırakıldı.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnek kullanır `gcnew` ileti nesnesi ayrılamadı.  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **Örnek**  
  
 Aşağıdaki örnek kullanır `gcnew` bir başvuru türü gibi kullanım için paketlenmiş değer türü oluşturun.  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **Output**  
  
```Output  
32  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)