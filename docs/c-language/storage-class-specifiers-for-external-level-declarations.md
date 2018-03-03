---
title: "Dış düzey bildirimleri depolama sınıfı tanımlayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- external definitions
- linkage [C++], external
- external linkage, variable declarations
- declaring variables, external variables
- declarations [C++], external
- declarations [C++], specifiers
- external declarations
- static variables, external declarations
- variables, visibility
- external linkage, storage-class specifiers
- referencing declarations
- visibility, variables
- static storage class specifiers
ms.assetid: b76b623a-80ec-4d5d-859b-6cef422657ee
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3764eb29cc46ec7b6159456131dde1024b187f61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="storage-class-specifiers-for-external-level-declarations"></a>Dış Düzey Bildirimleri Depolama Sınıfı Tanımlayıcıları
Dış değişkenler dosya kapsamında değişkenlerdir. Dışında herhangi bir işlev tanımlanır ve birçok işlevini potansiyel olarak kullanılabilir. İşlevler yalnızca dış düzeyinde tanımlanabilir ve bu nedenle, iç içe olamaz. Varsayılan olarak, dış değişkenleri ve işlevleri aynı ada sahip yapılan tüm başvuruları "dış bağlantı." sahip oldukları anlamına gelir aynı nesne başvuruları etkilenir. (Kullanabileceğiniz **statik** bu geçersiz kılma anahtar sözcüğü. Daha sonra daha fazla ayrıntı için bu bölümdeki bilgileri görebilirsiniz **statik**.)  
  
 Değişken bildirimleri dış düzeyinde ya da tanımları ("bildirimlerini tanımlama") değişkenlerin olan veya başka bir yerde ("bildirimlere başvurma") değişkenleri başvurular tanımlanmış.  
  
 Ayrıca (örtük veya açık olarak) değişkenini bir dış değişken bildirimi değişkenin tanımlayan bir bildirimidir. Dış düzeyinde bir tanımı çeşitli biçimlerde olabilir:  
  
-   İle bildirme bir değişken **statik** depolama sınıfı tanımlayıcısı. Açıkça başlatabilir **statik** açıklandığı gibi değişkeni sabit bir ifade ' [başlatma](../c-language/initialization.md). Başlatıcı atlarsanız, değişken varsayılan olarak 0 olarak başlatılır. Örneğin, bu iki ifade dikkate alınan her iki değişken tanımları olan `k`.  
  
    ```  
    static int k = 16;  
    static int k;  
    ```  
  
-   Dış düzeyinde açıkça başlatma değişkeni. Örneğin, `int j = 3;` değişkeni tanımıdır `j`.  
  
 Dış düzeyinde değişken bildirimlerden (diğer bir deyişle, tüm işlevleri dışında), kullanabileceğiniz **statik** veya `extern` depolama sınıfı tanımlayıcısı veya depolama sınıfı tanımlayıcısı tamamen çıkarın. Kullanamazsınız **otomatik** ve **kaydetmek** *depolama sınıfı tanımlayıcısı* dış düzeyinde Terminal.  
  
 Bir değişken dış düzeyinde tanımlandığında çeviri birim geri kalanı görünür olur. Değişkeni bildiriminden aynı kaynak dosyasında önce görünür değil. Bir başvuru bildirimi görünür, aşağıda açıklandığı gibi kolaylaştırır sürece Ayrıca, diğer program kaynak dosyalarında görünür değil.  
  
 İlgili kuralları **statik** içerir:  
  
-   Değişkenleri bildirilen tüm blokları dışında **statik** anahtar sözcüğü her zaman değerlerine program boyunca Beklet. Belirli çeviri birimine kendi erişimini kısıtlamak için kullanmanız gerekir **statik** anahtar sözcüğü. Bu "İç bağlantı." sağlar Tüm program Genel yapmak için açık depolama sınıfı eklemeyin veya anahtar sözcüğü kullanın `extern` (sonraki listesindeki kurallara bakın). Bu "dış bağlantı." sağlar İç ve dış bağlantı de açıklanmıştır [bağlantı](../c-language/linkage.md).  
  
-   Dış düzey yalnızca bir kez bir programdan konumundaki bir değişken tanımlayın. Aynı ada sahip başka bir değişken tanımlayın ve **statik** farklı çeviri birimindeki depolama sınıfı tanımlayıcısı. Her itibaren **statik** tanımıdır kendi çeviri biriminde yalnızca görünür hiçbir çakışması ortaya çıkar. Bu işlevler tek çeviri biriminin arasında paylaşılan, ancak diğer çeviri birimleri görünür olmalıdır tanımlayıcı adları gizlemek için kullanışlı bir yol sağlar.  
  
-   **Statik** depolama sınıfı tanımlayıcısı işlevlerini de uygulayabilirsiniz. Bir işlev bildirirseniz **statik**, adını da bildirilen dosya dışında görünmez olur.  
  
 Kullanmakla ilgili kuralları `extern` şunlardır:  
  
-   `extern` Depolama sınıfı tanımlayıcısı başka bir yerde tanımlanan bir değişken başvurusu bildirir. Kullanabileceğiniz bir `extern` bildirim tanımı başka bir kaynak dosyasında görünür hale getirmek için veya bir değişkeni aynı kaynak dosyasında tanımına önce görünür hale getirmek için. Dış düzeyinde değişkeni bir başvuru bildirdikten sonra bildirilen başvuru oluştuğu çeviri birim geri kalanı görünür bir değişkendir.  
  
-   İçin bir `extern` geçerli olması için başvuru, başvurduğu için değişken bir kez ve yalnızca bir kez dış düzeyinde tanımlanmalıdır. Bu tanımlama (olmadan `extern` depolama sınıfı) herhangi bir programı olun çeviri birimleri olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, dış bildirimler gösterir:  
  
```  
/******************************************************************  
                      SOURCE FILE ONE   
*******************************************************************/  
#include <stdio.h>  
  
extern int i;                // Reference to i, defined below   
void next( void );           // Function prototype              
  
int main()  
{  
    i++;  
    printf_s( "%d\n", i );   // i equals 4   
    next();  
}  
  
int i = 3;                  // Definition of i  
  
void next( void )  
{  
    i++;  
    printf_s( "%d\n", i );  // i equals 5  
    other();  
}  
  
/******************************************************************  
                      SOURCE FILE TWO   
*******************************************************************/  
#include <stdio.h>  
  
extern int i;              // Reference to i in   
                           // first source file   
void other( void )  
{  
    i++;  
    printf_s( "%d\n", i ); // i equals 6   
}  
```  
  
 Bu örnekte iki kaynak dosyaları üç dış bildirimlerini toplam içeren `i`. Yalnızca bir bildirimidir bir "tanımlama bildiriminin." Bu bildirimi  
  
```  
int i = 3;  
```  
  
 genel değişkeni `i` ve başlangıç değeri 3 ile başlatır. "Başvuru" bildirimi `i` ilk kaynak kullanarak dosya üst `extern` genel değişkeni dosyasında tanımlama bildiriminden önce görünür hale getirir. Başvuru bildirimi `i` ikinci kaynak dosyası da değişkeni görünür bu kaynak dosyasında hale getirir. Bir değişken için bir tanımlama örneği çeviri biriminde sağlanmazsa, derleyici olduğunu varsayar bir  
  
```  
extern int x;  
```  
  
 bildirim ve bir tanımlama başvuru başvurma  
  
```  
int x = 0;  
```  
  
 program başka bir çeviri biriminde görüntülenir.  
  
 Tüm üç işlevleri `main`, `next`, ve `other`, aynı görevi gerçekleştirmek: Bunlar artırmak `i` ve belgeyi yazdırabilirsiniz. 4, 5 ve 6 değerlerini yazdırılır.  
  
 Varsa değişkeni `i` değil olsaydı başlatılmadığı, onu 0'a otomatik olarak ayarlanacak. Bu durumda, 1, 2 ve 3 değerlerini yazdırılan. Bkz: [başlatma](../c-language/initialization.md) değişken başlatma hakkında bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Depolama Sınıfları](../c-language/c-storage-classes.md)