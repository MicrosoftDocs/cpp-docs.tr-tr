---
title: 'Nasıl yapılır: C + numaralandırmaları tanımlama ve kullanma +/ CLI | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f5c30b679b24e574d359a1f838785f0196f290d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131523"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Nasıl yapılır: C++/CLI üzerinde numaralandırmaları tanımlama ve kullanma
Bu konuda ele alınmıştır numaralandırmaları C + +/ CLI.  
  
## <a name="specifying-the-underlying-type-of-an-enum"></a>Enum temel türünü belirtme  
 Varsayılan olarak temel alınan bir numaralandırma türünde `int`.  Ancak, imzalı veya imzasız biçimlerinin olmasını türünü belirtebilirsiniz `int`, `short`, `long`, `__int32`, veya `__int64`.  Aynı zamanda `char`.  
  
```  
// mcppv2_enum_3.cpp  
// compile with: /clr  
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};  
  
int main() {  
   // fully qualified names, enumerator not injected into scope  
   day_char d = day_char::sun, e = day_char::mon;  
   System::Console::WriteLine(d);  
   char f = (char)d;  
   System::Console::WriteLine(f);  
   f = (char)e;  
   System::Console::WriteLine(f);  
   e = day_char::tue;  
   f = (char)e;  
   System::Console::WriteLine(f);  
}  
```  
  
 **Output**  
  
```Output  
sun  
0  
1  
2  
```  
  
## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>Yönetilen ve standart numaralandırmalar arasında dönüştürme  
 Bir numaralandırma ve tamsayı türü arasında standart dönüştürme yoktur; bir cast gereklidir.  
  
```  
// mcppv2_enum_4.cpp  
// compile with: /clr  
enum class day {sun, mon, tue, wed, thu, fri, sat};  
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum  
  
int main() {  
   day a = day::sun;  
   day2 = sun;  
   if ((int)a == day2)  
   // or...  
   // if (a == (day)day2)  
      System::Console::WriteLine("a and day2 are the same");  
   else  
      System::Console::WriteLine("a and day2 are not the same");  
}  
```  
  
 **Output**  
  
```Output  
a and day2 are the same  
```  
  
## <a name="operators-and-enums"></a>İşleçler ve numaralandırmalar  
 Aşağıdaki işleçleri geçerli Enum değerleri C + +/ CLI:  
  
|İşleç|  
|--------------|  
|== != \< > \<= >=|  
|+ -|  
|&#124; ^ & ~|  
|++ --|  
|sizeof|  
  
 İşleçler &#124; ^ & ~ ++--türleri bool dahil değil, temel alınan integral yalnızca sabit listeleri için tanımlanır.  Her iki işlenen numaralandırma türü olmalıdır.  
  
 Derleyici hiçbir statik veya dinamik bir enum işlem sonucunu denetimi yapar; bir işlem enum ait geçerli numaralandırıcılar aralık içinde değil değerinin neden olabilir.  
  
> [!NOTE]
>  C ++ 11 tanıtır yönetilen enum sınıfları C + önemli ölçüde farklı olan enum sınıf türleri yönetilmeyen kodunda +/ CLI. Özellikle, C ++ 11 enum sınıf türü aynı işleçleri yönetilen enum sınıf türü olarak C + desteklemez +/ CLI ve C + +/ CLI kaynak kodu sağlamalıdır yönetilen enum bir erişilebilirlik belirticisinin sınıf bildirimleri bunları yönetilmeyen (C++ içinden ayırt etmek için 11) enum sınıf bildirimleri. C + enum sınıfları hakkında daha fazla bilgi için +/ CLI, C + +/ CX ve C ++ 11, bkz: [enum sınıfı](../windows/enum-class-cpp-component-extensions.md).  
  
```  
// mcppv2_enum_5.cpp  
// compile with: /clr  
private enum class E { a, b } e, mask;  
int main() {  
   if ( e & mask )   // C2451 no E->bool conversion  
      ;  
  
   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)  
      ;  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```  
  
```  
// mcppv2_enum_6.cpp  
// compile with: /clr  
private enum class day : int {sun, mon};  
enum : bool {sun = true, mon = false} day2;  
  
int main() {  
   day a = day::sun, b = day::mon;  
   day2 = sun;  
  
   System::Console::WriteLine(sizeof(a));  
   System::Console::WriteLine(sizeof(day2));  
   a++;  
   System::Console::WriteLine(a == b);  
}  
```  
  
 **Output**  
  
```Output  
4  
1  
True  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Enum sınıfı](../windows/enum-class-cpp-component-extensions.md)