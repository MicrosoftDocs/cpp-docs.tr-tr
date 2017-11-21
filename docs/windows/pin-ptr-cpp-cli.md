---
title: pin_ptr (C + +/ CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs: C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c72149aa023723f4524ac22252f6778494341f44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)
Bildiren bir *sabitleme işaretçisi*, yalnızca ortak dil çalışma zamanı ile kullanılır.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 (Tüm çalışma zamanları için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 (Bu dil özelliği Windows çalışma zamanı'nda desteklenmiyor.)  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 A *sabitleme işaretçisi* nesne engelleyen iç işaretçi atık toplanan yığında taşıma verilir. Diğer bir deyişle, değer sabitleme işaretçisinin ortak dil çalışma zamanı tarafından değiştirilmez. Adres çözümlemesi yönetilmeyen işlev çağrısı sırasında beklenmedik bir şekilde değiştirmez Böylece yönetilmeyen bir işleve bir yönetilen sınıf adresini geçirdiğinizde, bu gereklidir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;  
```  
  
### <a name="parameters"></a>Parametreler  
 *cv_qualifier*  
 `const`veya `volatile` niteleyicileri. Varsayılan olarak, bir sabitleme işaretçidir `volatile`. Sabitleme işaretçisi bildirmek için hata değil yedek `volatile`.  
  
 *türü*  
 Türü `initializer`.  
  
 *var*  
 Adını `pin_ptr` değişkeni.  
  
 *Başlatıcı*  
 Bir başvuru türü, yönetilen bir dizi veya yerel bir işaretçi atayabilirsiniz herhangi bir nesne öğesinin üyesi.  
  
### <a name="remarks"></a>Açıklamalar  
 A `pin_ptr` yerel işaretçiden işlevselliğini üst temsil eder. Bu nedenle, yerel bir işaretçi atanabilir herhangi bir şey de atanabilir bir `pin_ptr`. İç işaretçi aynı işlemleri karşılaştırma ve işaretçi aritmetiği dahil olmak üzere yerel işaretçileri olarak gerçekleştirin izin verilir.  
  
 Bir nesne ya da yönetilen bir sınıfın alt nesne, bu durumda ortak dil çalışma zamanı, atık toplama sırasında taşımaz sabitlenmelidir. Bu asıl kullanımı, bir yönetilmeyen işlev çağrısı gerçek bir parametresi olarak yönetilen veri için bir işaretçi geçirmektir. Toplama döngüsü sırasında çalışma zamanı için sabitleme işaretçisi oluşturulan meta verileri inceler ve işaret öğe taşınmaz.  
  
 Bir nesneyi sabitleme değeri alanlarını sabitler; diğer bir deyişle, ilkel alanlarının veya değeri yazın. Ancak, alanları bildirilen izleme işleyicisi tarafından (`%`) değil sabitlenir.  
  
 Yönetilen bir nesne tanımlanan bir alt nesne sabitleme tüm nesneyi sabitleme etkisi vardır.  
  
 Sabitleme işaretçisi için yeni bir değer işaret edecek şekilde yeniden atandığında, işaret önceki örnek artık değerlendirilir sabitlenir.  
  
 Bir nesne sabitlenmiş ancak bir `pin_ptr` kendisine işaret eder. Sabitleme işaretçisi kapsamının dışına gider veya ayarlamak nesne artık sabitlenmiş [nullptr](../windows/nullptr-cpp-component-extensions.md). Sonra `pin_ptr` gider sabitlenmiştir nesne kapsam dışında taşınabilir yığınında atık toplayıcısı tarafından. Hala nesneye işaret tüm yerel işaretçileri güncelleştirilmez ve bunlardan birini XML'deki başvuran kurtarılamaz bir özel durum oluşturabilen.  
  
 Hiçbir sabitleme işaretçileri nesnesine noktası (tüm sabitleme işaretçileri kapsamının dışına çıktı, diğer nesnelere işaret edecek şekilde yeniden veya atanmış [nullptr](../windows/nullptr-cpp-component-extensions.md)), nesne Sabitlenmedi garanti edilmez.  
  
 Sabitleme işaretçisi bir başvuru tanıtıcısı, değer türü veya paketlenmiş türü tanıtıcısı, yönetilen tür üyesi ya da yönetilen bir dizi öğesi işaret edebilir. Bir başvuru türü işaret edemez.  
  
 Adresini alma bir `pin_ptr` yerel nesnesini noktalarına neden tanımsız davranış.  
  
 Sabitleme işaretçileri yığında yalnızca statik olmayan yerel değişkenleri olarak bildirilebilir.  
  
 Sabitleme işaretçileri olarak kullanılamaz:  
  
-   işlev parametreleri  
  
-   bir işlevin dönüş türü  
  
-   bir sınıf üyesi  
  
-   bir cast hedef türü.  
  
 `pin_ptr`içinde `cli` ad alanı. Daha fazla bilgi için bkz: [Platform, varsayılan ve cli ad alanları](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 İç işaretçiler hakkında daha fazla bilgi için bkz: [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md).  
  
 İşaretçileri sabitleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: PIN işaretçiler ve dizileri](../windows/how-to-pin-pointers-and-arrays.md) ve [nasıl yapılır: sabitleme işaretçileri bildirme ve değer türleri](../windows/how-to-declare-pinning-pointers-and-value-types.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnek kullanır `pin_ptr` için bir dizinin ilk öğesi konumunu belirtin.  
  
```  
// pin_ptr_1.cpp  
// compile with: /clr   
using namespace System;  
#define SIZE 10  
  
#pragma unmanaged  
// native function that initializes an array  
void native_function(int* p) {  
   for(int i = 0 ; i < 10 ; i++)  
    p[i] = i;  
}  
#pragma managed  
  
public ref class A {  
private:  
   array<int>^ arr;   // CLR integer array  
  
public:  
   A() {  
      arr = gcnew array<int>(SIZE);  
   }  
  
   void load() {  
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr  
   int* np = p;   // pointer to the first element in arr  
   native_function(np);   // pass pointer to native function  
   }  
  
   int sum() {  
      int total = 0;  
      for (int i = 0 ; i < SIZE ; i++)  
         total += arr[i];  
      return total;  
   }  
};  
  
int main() {  
   A^ a = gcnew A;  
   a->load();   // initialize managed array using the native function  
   Console::WriteLine(a->sum());  
}  
```  
  
 **Çıktı**  
  
```Output  
45  
```  
  
 **Örnek**  
  
 Aşağıdaki örnek, bir iç işaretçi sabitleme işaretçisi dönüştürülebilir ve dönüş adresi-of işleci yazın gösterir (`&`) işleneni yönetilen yığında iç işaretçi olur.  
  
```  
// pin_ptr_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   G() : i(1) {}  
   int i;  
};  
  
ref struct H {  
   H() : j(2) {}  
   int j;  
};  
  
int main() {  
   G ^ g = gcnew G;   // g is a whole reference object pointer  
   H ^ h = gcnew H;  
  
   interior_ptr<int> l = &(g->i);   // l is interior pointer  
  
   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer  
  
   k = l;   // ok  
   Console::WriteLine(*k);  
};  
```  
  
 **Çıktı**  
  
```Output  
1  
```  
  
 **Örnek**  
  
 Aşağıdaki örnek, sabitleme işaretçisi başka bir tür cast olduğunu gösterir.  
  
```  
// pin_ptr_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class ManagedType {  
public:  
   int i;  
};  
  
int main() {  
   ManagedType ^mt = gcnew ManagedType;  
   pin_ptr< int > pt = &mt->i;  
   *pt = 8;  
   Console::WriteLine(mt->i);  
  
   char *pc = ( char* ) pt;  
   *pc = 255;  
   Console::WriteLine(mt->i);  
}  
```  
  
 **Çıktı**  
  
```Output  
8  
255  
```