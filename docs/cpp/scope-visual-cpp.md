---
title: Kapsam (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 55baa4496522336a5a64ee81daa7a8ce484534c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="scope-visual-c"></a>Kapsam (Visual C++)
C++ adları bir programı yalnızca belirli bölgelerde kullanılabilir. Bu alan adı "scope" adı verilir. Statik kapsam nesne göstermiyor adı "ömrü" kapsamı belirler. Kapsam ayrıca sınıf oluşturucular ve Yıkıcılar çağrıldığında ve kapsama yerel değişkenleri hazırlarken bir ad görünürlüğünü belirler. (Daha fazla bilgi için bkz: [oluşturucular](../cpp/constructors-cpp.md) ve [Yıkıcılar](../cpp/destructors-cpp.md).) Kapsam beş tür vardır:  
  
-   **Yerel kapsam** bloğu içinde bildirilen bir ad yalnızca o bloğu ve onun ve yalnızca bildirim noktası sonra içine blokları içinde erişilebilir. İşlev gövdesi kapsayan bloğunun içine bildirilmiş sanki biçimsel bağımsız değişkenler işlevinin en dıştaki blok kapsamında bir işlev adları yerel kapsama sahip. Aşağıdaki kod parçası göz önünde bulundurun:  
  
    ```  
    {  
        int i;  
    }  
    ```  
  
     Çünkü bildirimi `i` küme ayraçları içine bir bloğu içinde `i` yerel kapsamına sahip ve isteğe bağlı olarak kod kapanış kuşak önce eriştiği için hiçbir zaman erişilebilir olduğunu.  
  
-   **İşlev kapsamı** etiketleridir işlevi kapsamında yalnızca adları. Bir işlev içinde herhangi bir kullanılabilir, ancak bu işlevin dışında erişilebilir değildir. İşlevlerin biçimsel bağımsız değişkenlerinin (işlev tanımlarında belirtilen bağımsız değişkenler), işlev gövdesinin en dıştaki bloğunun kapsamında olduğu kabul edilir.  
  
-   **Dosya kapsamı** dosya kapsamı tüm blokları veya sınıfları dışında bildirilen herhangi bir adı vardır. Bildiriminden sonra çeviri biriminde herhangi bir yerden erişilebilir. Statik nesneleri bildirme dosya kapsamı adlarıyla genel adlar genellikle denir.  
  
     C++'da, dosya kapsamı olarak da bilinen ad alanı kapsamı değil.  
  
-   **Sınıf kapsamı** sınıf üyeleri adlara sahip sınıf kapsamı. Sınıf üyesi işlevleri yalnızca üye seçim işleçleri kullanarak erişilebilir (**.** veya  **->** ) veya işaretçi-üye işleçleri (**.\***  veya  **-> \*** ) bir nesneye veya nesnenin o sınıfın; işaretçi statik olmayan sınıf üyesi verilerinin o sınıfın nesnesine yerel olarak kabul edilir. Aşağıdaki sınıf bildirimi göz önünde bulundurun:  
  
    ```  
    class Point  
    {  
        int x;  
        int y;  
    };  
    ```  
  
     Sınıf üyeleri `x` ve `y` sınıfı kapsamında değerlendirilir `Point`.  
  
-   **Prototip kapsamı** bir işlev prototipi bildirilen adları görünür yalnızca prototip sonuna kadar. Aşağıdaki prototipe üç adlarını bildirir (`strDestination`, `numberOfElements`, ve `strSource`); bu adları prototip sonunda kapsam dışında gidin:  
  
    ```  
    errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
    ```  
  
## <a name="hiding-names"></a>Adları Gizleme  
 Kapalı bir bloğunda bildirerek, bir ad gizleyebilirsiniz. Aşağıdaki şekilde `i` böylece ilişkili değişkeni gizleme iç bloğu içinde yeniden bildirilen `i` dış blok kapsamında.  
  
 ![Blok &#45; kapsam adı gizleme](../cpp/media/vc38sf1.png "vc38SF1")  
Kapsam engelleme ve gizleme adı  
  
 Çizimde gösterilen program çıktısı şöyledir:  
  
```  
i = 0  
i = 7  
j = 9  
i = 0  
```  
  
> [!NOTE]
>  Bağımsız değişken `szWhat` işlevi kapsamında olarak değerlendirilir. Bu nedenle, sanki işlevi en dıştaki bloğunda bildirilmiş değerlendirilir.  
  
## <a name="hiding-class-names"></a>Sınıf adları gizleme  
 Sınıf adları işlevi, nesne veya değişken veya aynı kapsamda Numaralandırıcı bildirerek gizleyebilirsiniz. Ancak, sınıf adı hala anahtar sözcüğüyle önekli olduğunda erişilip **sınıfı**.  
  
```  
// hiding_class_names.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
// Declare class Account at file scope.  
class Account  
{  
public:  
    Account( double InitialBalance )  
        { balance = InitialBalance; }  
    double GetBalance()  
        { return balance; }  
private:  
    double balance;  
};  
  
double Account = 15.37;            // Hides class name Account  
  
int main()  
{  
    class Account Checking( Account ); // Qualifies Account as   
                                       //  class name  
  
    cout << "Opening account with balance of: "  
         << Checking.GetBalance() << "\n";  
}  
//Output: Opening account with balance of: 15.37  
```  
  
> [!NOTE]
>  Herhangi bir sınıf adı yerleştirin (`Account`) dosya kapsamlı değişken hesabından ayırt etmek için anahtar sözcüğü sınıfı kullanılması için çağrılır. Kapsam çözümü işleci (:) sol tarafta sınıf adı ortaya çıktığında bu kuralın geçerli değildir. Kapsam çözümü işleci sol tarafındaki adları her zaman sınıf adları olarak kabul edilir.  
  
 Aşağıdaki örnek, bir nesne türü için bir işaretçi bildirmek gösterilmiştir `Account` kullanarak **sınıfı** anahtar sözcüğü:  
  
```  
class Account *Checking = new class Account( Account );  
```  
  
 `Account` Başlatıcı (parantez içinde) önceki deyiminde dosya kapsamı vardır; türü **çift**.  
  
> [!NOTE]
>  Bu örnekte gösterildiği gibi tanımlayıcı adları kullanılmasını zayıf programlama stili olarak kabul edilir.  
  
 İşaretçiler hakkında daha fazla bilgi için bkz: [türetilmiş türler](http://msdn.microsoft.com/en-us/aa14183c-02fe-4d81-95fe-beddb0c01c7c). Bildirim ve başlatma sınıfı nesneleri hakkında daha fazla bilgi için bkz: [sınıflar, yapılar ve birleşimleri](../cpp/classes-and-structs-cpp.md). Kullanma hakkında bilgi için **yeni** ve **silmek** serbest deposu işleçleri, bkz: [yeni ve delete işleçleri](new-and-delete-operators.md).  
  
## <a name="hiding-names-with-file-scope"></a>Dosya kapsamı adlarıyla gizleme  
 Blok kapsamında aynı adı açıkça bildirerek dosya kapsamı ile adları gizleyebilirsiniz. Bununla birlikte, dosya kapsam adlarına kapsam çözünürlük işleci (`::`) kullanılarak erişilebilir.  
  
```  
// file_scopes.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int i = 7;   // i has file scope, outside all blocks  
using namespace std;  
  
int main( int argc, char *argv[] ) {  
   int i = 5;   // i has block scope, hides i at file scope  
   cout << "Block-scoped i has the value: " << i << "\n";  
   cout << "File-scoped i has the value: " << ::i << "\n";  
}  
```  
  
```Output  
Block-scoped i has the value: 5  
File-scoped i has the value: 7  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel kavramlar](../cpp/basic-concepts-cpp.md)