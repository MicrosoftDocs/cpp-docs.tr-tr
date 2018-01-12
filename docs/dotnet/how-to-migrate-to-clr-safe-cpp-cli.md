---
title: "Nasıl yapılır: - clr geçirme: Güvenli (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- migration [C++], verifiable assemblies
- upgrading Visual C++ applications, verifiable assemblies
- verifiable assemblies [C++], migrating to
- /clr compiler option [C++], migrating to /clr:safe
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c9d28d64b450d14ba1579597f0276cfe3a0cf39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-migrate-to-clrsafe-ccli"></a>Nasıl yapılır: /clr:safe'e Geçiş (C++/CLI)
Visual C++ kullanarak doğrulanabilir bileşenler oluşturabilir **/CLR: safe**, derleyicinin her doğrulanabilen olmayan kod yapı hataları oluşturmasına neden olur.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki sorunlar verifiability hatalar oluşturur:  
  
-   Yerel türler. Kullanılan değil olsa bile yerel sınıflar, yapılar, işaretçileri veya diziler bildirimi derleme engeller.  
  
-   Genel değişkenler  
  
-   Ortak dil çalışma zamanı işlev çağrıları dahil olmak üzere herhangi bir yönetilmeyen kitaplığı işlev çağrılarını  
  
-   Doğrulanabilir bir işlev içeremez bir [static_cast işleci](../cpp/static-cast-operator.md) aşağı atama için. [Static_cast işleci](../cpp/static-cast-operator.md) aşağı-atama, yanı sıra, ilkel türler arasında atama için kullanılan [safe_cast](../windows/safe-cast-cpp-component-extensions.md) veya C tarzı cast (olarak uygulanan bir [safe_cast](../windows/safe-cast-cpp-component-extensions.md)) kullanılması gerekir.  
  
-   Doğrulanabilir bir işlev içeremez bir [reinterpret_cast işleci](../cpp/reinterpret-cast-operator.md) (veya tüm C tarzı dönüştürme eşdeğeri).  
  
-   Doğrulanabilir bir işlev üzerinde aritmetik gerçekleştiremiyor bir [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md). Yalnızca atayın ve başvurabilir.  
  
-   Doğrulanabilir bir işlev yalnızca throw veya değer türleri atmadan önce Kutulu gerekir böylece başvuru türleri işaretçiler yakalayın.  
  
-   Doğrulanabilir bir işlev yalnızca doğrulanabilir işlevleri çağırabilir (ortak dil çalışma zamanı için çağrılarına izin verilmiyor şekilde dahil `AtEntry` / `AtExit`, ve genel oluşturucular izin verilmeyen şekilde).  
  
-   Doğrulanabilen bir sınıf kullanamazsınız <xref:System.Runtime.InteropServices.LayoutKind>.  
  
-   Bir EXE oluşturuluyorsa, ana işlevi herhangi bir parametre, bu nedenle bildiremezsiniz <xref:System.Environment.GetCommandLineArgs%2A> komut satırı bağımsız değişkenlerini almak için kullanılması gerekir.  
  
-   Sanal olmayan bir sanal işlev çağrısı yapılıyor. Örneğin:  
  
    ```  
    // not_verifiable.cpp  
    // compile with: /clr  
    ref struct A {  
       virtual void Test() {}  
    };  
  
    ref struct B : A {};  
  
    int main() {  
       B^ b1 = gcnew B;  
       b1->A::Test();   // Non-virtual call to virtual function  
    }  
    ```  
  
 Ayrıca, aşağıdaki anahtar sözcükler doğrulanabilir kod içinde kullanılamaz:  
  
-   [Yönetilmeyen](../preprocessor/managed-unmanaged.md) ve [paketi](../preprocessor/pack.md) pragmaları  
  
-   [naked](../cpp/naked-cpp.md) ve [Hizala](../cpp/align-cpp.md) [__declspec](../cpp/declspec.md) değiştiricileri  
  
-   [__asm](../assembler/inline/asm.md)  
  
-   [__based](../cpp/based-grammar.md)  
  
-   [__try](../cpp/try-except-statement.md) ve`__except`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)