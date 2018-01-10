---
title: "#<a name=\"define-directive-cc--microsoft-docs\"></a>define yönergesi (C/C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#define'
dev_langs: C++
helpviewer_keywords:
- define directive (#define), syntax
- preprocessor, directives
- define directive (#define)
- '#define directive, syntax'
- '#define directive'
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a42b1b823ac69ba9a92535076ba8ec45f6c9710d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="define-directive-cc"></a>#define Yönergesi (C/C++)
`#define` Oluşturur bir *makrosu*, bir belirteç dizesi ilişkide bir tanımlayıcı veya parametreli tanımlayıcısı olduğu. Makro tanımlandıktan sonra kaynak dosya tanımlayıcıda her örneği için belirteç dizesini derleyici yerine kullanabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
 `#define`*tanımlayıcısı* *belirteci dize*iptal et  
  
 `#define`*tanımlayıcısı* `(` *tanımlayıcısı*kabul`,`*...*  `,` *tanımlayıcısı*kabul`)`*belirteci dize*iptal et  
  
## <a name="remarks"></a>Açıklamalar  
 `#define` Yönergesi neden yerine derleyici *belirteci dize* her örneği için *tanımlayıcısı* kaynak dosyasında. *Tanımlayıcısı* yalnızca bir belirteç oluşturduğunda değiştirilir. Diğer bir deyişle, *tanımlayıcısı* dize ya da daha uzun bir tanımlayıcı bir parçası olarak bir açıklama görünüyorsa değiştirilmez. Daha fazla bilgi için bkz: [belirteçleri](../cpp/tokens-cpp.md).  
  
 *Belirteci dize* bağımsız değişkeni bir dizi anahtar sözcükler, sabitleri veya tam deyimleri gibi belirteçleri oluşur. Gereken bir veya daha fazla boşluk karakterleri ayrı *belirteci dize* gelen *tanımlayıcısı*. Bu boşluk yedek metin parçası olarak kabul edilmez veya metnin son belirteç izleyen hiçbir boşluk değil.  
  
 A `#define` olmadan bir *belirteci dize* kaldırır *tanımlayıcısı* kaynak dosyadan. *Tanımlayıcısı* kalır tanımlanan ve kullanılarak test `#if defined` ve `#ifdef` yönergeleri.  
  
 İkinci sözdizimi işlevi benzeri makrosu parametrelerle biçimini tanımlar. Bu form parantez içinde yer almalıdır parametreleri isteğe bağlı bir listesini kabul eder. Makro tanımlanan, her sonraki geçişi tamamlandıktan sonra *tanımlayıcısı*( *tanımlayıcısı*opt,..., *tanımlayıcısı*opt) bir sürümü ile değiştirilir  *belirteç dizesini* resmi parametrelerini yerine gerçek bağımsız değişkenlere sahiptir bağımsız değişkeni.  
  
 Biçimsel parametresi adları görünür *belirteci dize* yeri gerçek değerler yerine konumlarını işaretler. Birden çok kez görüntülenebilir her parametre adı *belirteci dize*, ve adlarını herhangi bir sırada yer alabilir. Çağrısında bağımsız değişken sayısı makro tanımındaki parametre sayısı aynı olmalıdır. Ayraç serbest kullanımı karmaşık gerçek bağımsız değişkenler doğru yorumlanması güvence altına alır.  
  
 Listedeki biçimsel parametresi virgülle ayrılır. Listedeki her bir adı benzersiz olmalıdır ve liste parantez içine alınmalıdır. Boşluk ayırabilirsiniz *tanımlayıcısı* ve parantez. Satır birleştirme kullanın — bir ters eğik çizgi koyun (`\`) yeni satır karakteri hemen önce — birden çok kaynak satırlarındaki uzun yönergeleri için. Biten yeni satırına biçimsel parametresi adı kapsamını genişletir *belirteci dize*.  
  
 Makro ikinci sözdizimi biçiminde tanımlandığında ardında bir bağımsız değişken listesi sonraki metinsel örnekleri makrosu çağrı gösterir. Bir örneği aşağıdaki gerçek bağımsız değişkenler *tanımlayıcısı* kaynak dosyasına resmi parametrelerini makro tanımı ilgili eşleştirilir. Her biçimsel parametresi *belirteci dize* değil öncesi bir dizeleyen (`#`), karakterleştirme (`#@`), veya belirteç yapıştıran (`##`) işleci veya tarafından izlenmeyen bir `##` işlecidir karşılık gelen gerçek bağımsız değişkeni tarafından değiştirildi. Biçimsel parametresi yönergesi değiştirir önce makroların gerçek bağımsız genişletilir. (İşleçleri açıklanan [önişlemci işleçleri](../preprocessor/preprocessor-operators.md).)  
  
 İkinci biçiminde bağımsız değişkenlerle makroları aşağıdaki örnekleri göstermeye `#define` sözdizimi:  
  
```  
// Macro to define cursor lines   
#define CURSOR(top, bottom) (((top) << 8) | (bottom))  
  
// Macro to get a random integer with a specified range   
#define getrandom(min, max) \  
    ((rand()%(int)(((max) + 1)-(min)))+ (min))  
```  
  
 Yan etkileri olan bağımsız değişkenler, bazen beklenmeyen sonuçlara neden makroları neden olur. Belirli bir biçimsel parametresi birden fazla kez görünebilir *belirteci dize*. Bu biçimsel parametresi yan etkileri olan bir ifade olarak değiştirirse, onun yan etkileri olan birden fazla kez ifadenin. (Altında örneklere bakın [belirteç yapıştıran işleç (#)](../preprocessor/token-pasting-operator-hash-hash.md).)  
  
 `#undef` Yönergesi unutulursa için bir tanımlayıcının önişlemci tanımı neden olur. Bkz: [#undef yönergesi](../preprocessor/hash-undef-directive-c-cpp.md) daha fazla bilgi için.  
  
 İçinde tanımlanan makro adını oluşursa *belirteci dize* (hatta başka bir makrosu genişletmesi sonucu olarak), onu genişletilmemiş.  
  
 İkinci bir `#define` ikinci belirteci sırası ilk aynı olmadığı sürece aynı ada sahip bir makro bir uyarı üretir.  
  
 **Microsoft özel**  
  
 Microsoft C/C++ yeni tanımı orijinal tanımına sözdizimsel olarak aynı ise makro yeniden tanımlamanız olanak sağlar. Diğer bir deyişle, iki tanımları farklı parametre adları olabilir. Bu davranış farklı [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] C iki tanımları sözcüksel olarak aynı olmasını gerektirir.  
  
 Örneğin, aşağıdaki iki makroları dışında parametre adları aynıdır. [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)]C böyle bir şemadaki izin vermez ancak isteğe bağlı olarak Microsoft C/C++ hatasız derler.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( a1 * a2 )  
```  
  
 Öte yandan, aşağıdaki iki makroları özdeş değil ve Microsoft C/C++ içinde bir uyarı oluşturur.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( b1 * b2 )  
```  
  
 **SON Microsoft özel**  
  
 Bu örnekte gösterilmiştir `#define` yönergesi:  
  
```  
#define WIDTH       80  
#define LENGTH      ( WIDTH + 10 )  
```  
  
 İlk ifade tanımlayıcısını tanımlar `WIDTH` sabit 80 tamsayı olarak ve tanımlar `LENGTH` cinsinden `WIDTH` ve tamsayı sabit 10. Her oluşumu `LENGTH` değiştirilir (`WIDTH + 10`). Kapatma içinde her oluşumu `WIDTH + 10` ifadeyle değiştirilir (`80 + 10`). Parantezler `WIDTH + 10` aşağıdaki gibi deyimlerinde yorumlama denetlemek için önemlidir:  
  
```  
var = LENGTH * 20;  
```  
  
 Ön işleme aşama sonra deyimi olur:  
  
```  
var = ( 80 + 10 ) * 20;  
```  
  
 hangi 1800 için değerlendirir. Parantez olmadan oluşur:  
  
```  
var = 80 + 10 * 20;  
```  
  
 hangi 280 için değerlendirir.  
  
 **Microsoft özel**  
  
 Makrolar ve sabitler ile tanımlama [/D](../build/reference/d-preprocessor-definitions.md) derleyici seçeneği kullanarak aynı etkiye sahip bir `#define` dosyanızı başlangıcında önişlem yönergesi. En fazla 30 makroları /D seçeneği kullanılarak tanımlanabilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)