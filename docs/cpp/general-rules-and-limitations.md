---
title: Genel kurallar ve sınırlamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1b3c3048bbd335fa43113c6d8876824475ad925
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408495"
---
# <a name="general-rules-and-limitations"></a>Genel Kurallar ve Sınırlamalar
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
  
-   Bir işlevi bildirmek veya olmadan nesne **dllimport** veya **dllexport** özniteliği, işlev veya nesne DLL arabiriminin bir parçası dikkate alınmaz. Bu nedenle, bir işlevin veya nesnenin tanımı bu modüldeki veya başka bir modül aynı programın içinde mevcut olması gerekir. DLL arabirimi bir işlevin veya nesnenin parçası haline getirmek için işlevin veya nesnenin başka bir modül tanımını bildirmek **dllexport**. Aksi halde bir bağlayıcı hatası meydana gelir.  
  
     Bir işlevi bildirmek veya nesnesi ile **dllexport** özniteliği, tanımı aynı programın bazı modülünde görünmesi gerekir. Aksi halde bir bağlayıcı hatası meydana gelir.  
  
-   Programınızı tek bir modülde hem de içeriyorsa **dllimport** ve **dllexport** bildirimleri için aynı işlev ya da nesneye **dllexport** özniteliği önceliklidir üzerinden **dllimport** özniteliği. Ancak, bir derleyici uyarısı oluşturulur. Örneğin:  
  
    ```cpp 
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   C++'da genel olarak bildirilen veya statik yerel veriler işaretçi başlatabilir veya ile bildirilen bir veri nesnesi adresi ile **dllimport** özniteliği, c dilinde bir hata oluşturur Ayrıca, bir statik yerel işlev işaretçisi ile bildirilen bir işlevi adresi ile başlatabilir **dllimport** özniteliği. C'de, böyle bir atama işaretçiyi DLL alma dönüştürücü (Denetim işleve aktaran bir kod saplama) adresine yerine işlevin adresini ayarlar. C++'da, işaretçi için işlevin adresini ayarlar. Örneğin:  
  
    ```cpp 
    __declspec( dllimport ) void func1( void );  
    __declspec( dllimport ) int i;  
  
    int *pi = &i;                             // Error in C  
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,  
                                              // function in C++  
  
    void func2()  
    {  
       static int *pi = &i;                  // Error in C  
       static void ( *pf )( void ) = &func1; // Address of thunk in C,  
                                             // function in C++  
    }  
    ```  
  
     Ancak, bir program içerdiğinden **dllexport** nesne bildirimi özniteliğinde programda bir yere bu nesne için tanım sağlamalıdır, genel veya yerel statik işlev işaretçisi ile başlatabilirsiniz. adresini bir **dllexport** işlevi. Benzer şekilde, bir genel veya yerel statik veri işaretçisine adresiyle başlatabilirsiniz bir **dllexport** veri nesnesi. Örneğin, C veya C++ ortamında aşağıdaki kod hatalar oluşturmaz:  
  
    ```cpp 
    __declspec( dllexport ) void func1( void );  
    __declspec( dllexport ) int i;  
  
    int *pi = &i;                              // Okay  
    static void ( *pf )( void ) = &func1;      // Okay  
  
    void func2()  
    {  
        static int *pi = &i;                   // Okay  
        static void ( *pf )( void ) = &func1;  // Okay  
    }  
    ```  
  
-   Uygularsanız, **dllexport** olarak işaretlenmemiş bir temel sınıf olan normal bir sınıfa **dllexport**, derleyicinin C4275 oluşturur.  
  
     Derleyici, temel sınıf bir sınıf şablonunun bir özelleştirmesi ise aynı uyarı oluşturur. Bu sorunu çözmek için temel sınıf ile işaretle **dllexport**. Bir sınıf şablonunun bir özelleştirmesi nereye yerleştireceğinizi sorundur **__declspec(dllexport)**; sınıf şablonu işaretlemek izin verilmez. Bunun yerine, açıkça sınıf şablonu örneği oluşturun ve bu açık örnek oluşturma ile işaretle **dllexport**. Örneğin:  
  
    ```cpp 
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     Bu çözüm, şablon bağımsız değişken sınıf ise başarısız olur. Örneğin:  
  
    ```cpp 
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     Bu ortak desen şablonları ile olduğundan derleyici semantiği değiştirilen **dllexport** bir veya daha fazla temel sınıf olan bir sınıfa uygulandığında ve bir veya daha fazla temel sınıflar, sınıf şablonunun bir özelleştirmesi olduğunda . Bu durumda, derleyici örtük olarak geçerlidir **dllexport** sınıf şablonlarının uzmanlıkları için. Aşağıdakileri yapın ve bir uyarı alırsınız değil:  
  
    ```cpp 
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)