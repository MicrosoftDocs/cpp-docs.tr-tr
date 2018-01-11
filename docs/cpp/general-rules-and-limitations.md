---
title: "Genel kurallar ve sınırlamalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51f92844e993671a3423c04523ccf4e03f7f7e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="general-rules-and-limitations"></a>Genel Kurallar ve Sınırlamalar
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
  
-   Bir işlev bildirme ya da olmadan nesne **dllimport** veya `dllexport` özniteliği, işlev veya nesne DLL arabiriminin parçası dikkate alınmaz. Bu nedenle, işlev veya nesne tanımı bu modül veya başka bir modül aynı programının mevcut olması gerekir. DLL arabirimi işlevi veya nesne parçası haline getirmek için işlevi veya başka bir modül nesnesinin tanımı bildirme `dllexport`. Aksi halde, bir bağlayıcı hatası oluşturulur.  
  
     Bir işlev bildirme ya da nesnesi ile `dllexport` özniteliği, tanımına aynı program bazı modülünde yer almalıdır. Aksi halde, bir bağlayıcı hatası oluşturulur.  
  
-   Programınızı tek bir modüldeki her ikisi de içeriyorsa **dllimport** ve `dllexport` bildirimler aynı işlevi veya nesnesi, `dllexport` özniteliği önceliklidir **dllimport** özniteliği. Ancak, bir derleyici uyarısı oluşturulur. Örneğin:  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   C++'da, genel olarak bildirilen veya statik yerel veri işaretçi başlatabilir veya adresi ile bildirilen bir veri nesnesi ile **dllimport** c dilinde bir hata oluşturur özniteliği Ayrıca, bir statik yerel işlev işaretçisi ile bildirilen işlevinin adresiyle başlatabilir **dllimport** özniteliği. C, bu tür atama işlev adresi yerine işaretçiyi DLL içeri aktarma dönüştürücü (Denetim işleve aktaran bir kod saplama) adresine ayarlar. C++'da, işaretçi işlevi adresine ayarlar. Örneğin:  
  
    ```  
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
  
     Ancak, bir program içerdiği için `dllexport` bir nesnesinin bildirimi özniteliğinde, o nesneyi yere programda tanımı sağlamalıdır, genel veya yerel statik işlev işaretçisi bir adresiylebaşlatabilir`dllexport`işlevi. Benzer şekilde, bir genel veya yerel statik verileri işaretçi adresiyle başlatabilir bir `dllexport` veri nesnesi. Örneğin, C veya C++ aşağıdaki kod hataları oluşturmaz:  
  
    ```  
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
  
-   Uygularsanız `dllexport` olarak işaretlenmemiş bir temel sınıfı olan normal bir sınıfa `dllexport`, derleyici C4275 oluşturur.  
  
     Taban sınıfı bir sınıf şablonu uzmanlaşması ise derleyici aynı uyarı oluşturur. Bu sorunu çözmek için temel sınıf ile işaretle `dllexport`. Sınıf şablonu uzmanlaşması nereye sorundur **__declspec(dllexport)**; sınıf şablonu işaretlemek izin verilmiyor. Bunun yerine, açıkça sınıf şablonu oluşturmak ve bu açık örnekleme ile işaretle `dllexport`. Örneğin:  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     Şablon bağımsız değişken türetme sınıfı ise bu geçici çözüm başarısız olur. Örneğin:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     Bu şablonları ortak desenle olduğundan derleyici semantiği değiştirildi `dllexport` bir veya daha fazla taban sınıfları sahip bir sınıfa uygulandığında ve bir veya daha fazla temel sınıflar sınıf şablonu uzmanlaşması olduğunda. Bu durumda, derleyici örtük olarak geçerlidir `dllexport` sınıf şablonları özelleştirmeleri için. Aşağıdakileri yapın ve bir uyarı almamış:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)