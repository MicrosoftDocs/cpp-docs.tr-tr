---
title: interior_ptr (C + +/ CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- stdcli::language::interior_ptr
- interior_ptr_cpp
- interior_ptr
dev_langs: C++
helpviewer_keywords: interior_ptr keyword [C++]
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: edb506b17cce617c438bc518bfbd5410b9dabbe2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="interiorptr-ccli"></a>interior_ptr (C++/CLI)
Bir *iç işaretçi* bir işaretçi bir başvuru türü içinde ancak nesne bildirir. Bir başvuru tanıtıcısı, değer türü, paketlenmiş türü tanıtıcısı, yönetilen tür üyesi veya yönetilen bir dizi bir öğe için bir iç işaretçi işaret edebilir.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 (Tüm çalışma zamanları için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 (Yalnızca Windows çalışma zamanı için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 Aşağıdaki sözdizimi örneği iç işaretçi gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
cli::interior_ptr<cv_qualifier type> var = &initializer;  
```  
  
### <a name="parameters"></a>Parametreler  
 *cv_qualifier*  
 **const** veya `volatile` niteleyicileri.  
  
 *türü*  
 Türü *Başlatıcı*.  
  
 *var*  
 Adını `interior_ptr` değişkeni.  
  
 *Başlatıcı*  
 Bir başvuru türü, yönetilen bir dizi veya yerel bir işaretçi atayabilirsiniz herhangi bir nesne öğesinin üyesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerel bir işaretçi bir öğe, bir nesne örneklerini taşıma atıktoplayıcı sonuçları yönetilen yığında kendi konumu değişiklikleri izleyebilmesi için değil. Doğru örneğine başvuru yapmak bir işaretçi için sırayla çalışma zamanı yeni konumlandırılmış nesnesine işaretçi güncelleştirmesi gerekir.  
  
 Bir `interior_ptr` yerel işaretçiden işlevselliğini üst temsil eder.  Bu nedenle, yerel bir işaretçi atanabilir herhangi bir şey de atanabilir bir `interior_ptr`.  İç işaretçi aynı işlemleri karşılaştırma ve işaretçi aritmetiği dahil olmak üzere yerel işaretçileri olarak gerçekleştirin izin verilir.  
  
 İç işaretçi yalnızca yığında bildirilebilir.  İç işaretçi bir sınıf üyesi olarak bildirilemez.  
  
 İç işaretçiler yalnızca yığında olduğundan, bir iç işaretçi adresini bir yönetilmeyen işaretçi verir.  
  
 `interior_ptr`örtük bir dönüştürme sahip `bool`, böylece kullanımını koşullu deyimler için.  
  
 Çöp toplanan yığında taşınamaz bir nesneye işaret eden iç işaretçi bildirme hakkında daha fazla bilgi için bkz: [pin_ptr](../windows/pin-ptr-cpp-cli.md).  
  
 `interior_ptr`CLI ad alanıdır.  Bkz: [Platform, varsayılan ve cli ad alanları](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) daha fazla bilgi için.  
  
 İç işaretçiler hakkında daha fazla bilgi için bkz:  
  
-   [Nasıl yapılır: bildirme ve iç işaretçiler ve yönetilen diziler kullanma (C + +/ CLI)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)  
  
-   [Nasıl yapılır: interior_ptr anahtar sözcüğü ile değer türleri bildirme (C + +/ CLI)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)  
  
-   [Nasıl yapılır: iç işaretçiler ve yerel işaretçilerle işlevleri tekrar yükleme (C + +/ CLI)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)  
  
-   [Nasıl yapılır: const anahtar sözcüğü ile iç işaretçileri bildirme (C + +/ CLI)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnek bildirme ve iç işaretçi bir başvuru türü nasıl kullanılacağını gösterir.  
  
```cpp  
// interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   int data;  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   h_MyClass->data = 1;  
   Console::WriteLine(h_MyClass->data);  
  
   interior_ptr<int> p = &(h_MyClass->data);  
   *p = 2;  
   Console::WriteLine(h_MyClass->data);  
  
   // alternatively  
   interior_ptr<MyClass ^> p2 = &h_MyClass;  
   (*p2)->data = 3;  
   Console::WriteLine((*p2)->data);  
}  
```  
  
 **Çıktı**  
  
```Output  
1  
2  
3  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)