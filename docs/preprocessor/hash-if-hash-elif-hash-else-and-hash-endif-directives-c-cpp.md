---
title: '#Eğer, #elif, #else ve #endif yönergeleri (C/C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#else'
- '#endif'
- '#if'
- '#elif'
- defined
- __has_include
dev_langs:
- C++
helpviewer_keywords:
- '#elif directive'
- conditional compilation, directives
- endif directive (#endif)
- preprocessor, directives
- '#else directive'
- '#endif directive'
- if directive (#if)
- else directive (#else)
- '#if directive'
- elif directive (#elif)
- defined directive
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9d4f941298159b8a3ea1aa3fe37efd1e6dc68ab
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if, #elif, #else ve #endif Yönergeleri (C/C++)
`#if` İle yönerge `#elif`, `#else`, ve `#endif` yönergeleri, denetimleri derleme kaynak dosyası kısımlarının. İfade yazma (sonra `#if`) hemen ardından satır grubu sıfır olmayan bir değere sahip `#if` yönergesi çevirisi biriminde tutulur.  
  
## <a name="grammar"></a>Dilbilgisi  
 *Koşullu* :  
 *IF-bölümü elif parçaları*kabul*else bölümünü*kabul*endif satır*  
  
 *IF-bölümü* :  
 *Eğer satırlı metin*  
  
 *IF-line* :  
 **#if**  *constant-expression*  
  
 **#ifdef***tanımlayıcısı*   
  
 **#ifndef***tanımlayıcısı*   
  
 *elif bölümleri* :  
 *elif satırlı metin*  
  
 *elif bölümleri elif satırlı metin*  
  
 *elif satır* :  
 **#elif**  *constant-expression*  
  
 *else bölümünü* :  
 *satırı başka metin*  
  
 *satırı başka* :  
 `#else`  
  
 *Satır içi endif* :  
 `#endif`  
  
 Her `#if` bir kapanış tarafından kaynak dosyası yönergesinde eşleşen `#endif` yönergesi. Herhangi bir sayıda `#elif` yönergeleri arasında görünebilir `#if` ve `#endif` yönergeleri, ancak en çok bir `#else` yönergesi izin verilir. `#else` Yönergesi, varsa, olmalıdır önce son yönergesi `#endif`.  
  
 `#if`, `#elif`, `#else`, Ve `#endif` yönergeleri, diğer metin bölümlerini iç içe `#if` yönergeleri. Her iç içe geçmiş `#else`, `#elif`, veya `#endif` yönergesi ait en yakın önceki `#if` yönergesi.  
  
 Tüm koşullu derleme yönergeleri gibi `#if` ve **#ifdef**, kapatma ile eşleşmesi gerekir `#endif` yönergeleri önce dosyanın sonuna; Aksi takdirde bir hata iletisi oluşturulur. Koşullu derleme yönergeleri dahil etme dosyalarda, aynı koşulları karşılamalıdır: hiçbir eşleşmeyen koşullu derleme yönergeleri içeren dosyanın sonunda olması gerekir.  
  
 Makro değiştirme aşağıdaki komut satırını bölümü içinde gerçekleştirilen bir `#elif` makrosu çağrı olarak kullanılabilmesi için komut *sabit ifadesi*.  
  
 Önişlemci verilen oluşumlarını birini seçer *metin* başka bir işleme için. Belirtilen bir blok *metin* metin herhangi bir dizi olabilir. Birden fazla satır kaplar. Genellikle *metin* derleyici veya önişlemci anlamlıdır program metindir.  
  
 Önişlemci seçili işler *metin* ve derleyiciye geçirir. Varsa *metin* önişlemci yönergeleri, bu yönergeleri önişlemci tıklatıldığındaki içerir. Önişlemci tarafından seçilen metin blokları derlenir.  
  
 Tek bir ön işlemci seçer *metin* her aşağıdaki sabit ifade değerlendirme tarafından öğesi `#if` veya `#elif` true (sıfır) sabit bir ifade bulana kadar yönergesi. Tüm metni seçer (itibaren diğer önişlemci yönergeleri de dahil olmak üzere **#**), ilişkili kadar `#elif`, `#else`, veya `#endif`.  
  
 Varsa tüm oluşumlarını *sabit ifadesi* yanlışsa, veya yoksa `#elif` yönergeleri görüntülenir, sonra metin bloğu önişlemci seçer `#else` yan tümcesi. Varsa `#else` yan tümcesi atlanırsa ve tüm örneklerini *sabit ifadesi* içinde `#if` blok false, herhangi bir metin engelleme seçilir.  
  
 *Sabit ifadesi* bu ek kısıtlamalar ile tamsayı sabit ifade:  
  
-   İfadeler Tamsayı türünde olmalıdır ve karakter sabitleri yalnızca tamsayı sabitleri içerebilir ve **tanımlanan** işleci.  
  
-   İfade kullanamazsınız `sizeof` veya bir tür atama işleci.  
  
-   Hedef ortamdaki tüm aralıklarını tamsayıların temsil etmek mümkün olmayabilir.  
  
-   Çeviri türünü temsil eder `int` türle aynı **uzun**, ve `unsigned int` aynı `unsigned long`.  
  
-   Çevirici kod değerleri hedef ortam için kümesinden farklı bir dizi karakter sabitleri çevirebilir. Hedef ortam özelliklerini belirlemek için SINIRLARI makrolarından değerlerini denetleyin. Hedef ortamı için yerleşik bir uygulamada H.  
  
-   İfade tüm ortam sorguları gerçekleştirmelisiniz değil ve hedef bilgisayarda uygulama ayrıntıları yalıtılmış kalmalıdır.  

## <a name="defined"></a>tanımlanmış  
 Önişlemci işleci **tanımlanan** özel sabit ifadeler, aşağıdaki sözdizimi tarafından gösterildiği gibi kullanılabilir:  
  
 tanımlı ( `identifier` )  
  
 Tanımlı `identifier`  
  
 Bu sabit bir ifade olarak kabul true (sıfır) varsa *tanımlayıcısı* şu anda tanımlı; Aksi halde, koşul yanlış olduğunda (0). Tanımlı boş metin olarak kabul edilir olarak tanımlanan bir tanımlayıcı. **Tanımlanan** yönergesi olarak kullanılabilir bir `#if` ve bir `#elif` yönergesi, ancak başka saklanıyorsa.  
  
 Aşağıdaki örnekte, `#if` ve `#endif` yönergeleri kontrol üç işlev çağrılarını birinin derleme:  
  
```  
#if defined(CREDIT)  
    credit();  
#elif defined(DEBIT)  
    debit();  
#else  
    printerror();  
#endif  
```  
  
 İşlev çağrısı `credit` varsa derlenmiş tanımlayıcı `CREDIT` tanımlanır. Varsa tanımlayıcı `DEBIT` tanımlanır, işlev çağrısı `debit` derlenir. Hiçbiri tanımlayıcı tanımlanmışsa çağrısı `printerror` derlenir. Unutmayın `CREDIT` ve `credit` , çalışmalarına farklı olduğu için ayrı C ve C++ tanımlayıcılardır.  
  
 Aşağıdaki örnek koşullu derleme ifadeler adlı önceden tanımlanmış bir simgesel sabiti varsayın `DLEVEL`.  
  
```  
#if DLEVEL > 5  
    #define SIGNAL  1  
    #if STACKUSE == 1  
        #define STACK   200  
    #else  
        #define STACK   100  
    #endif  
#else  
    #define SIGNAL  0  
    #if STACKUSE == 1  
        #define STACK   100  
    #else  
        #define STACK   50  
    #endif  
#endif  
#if DLEVEL == 0  
    #define STACK 0  
#elif DLEVEL == 1  
    #define STACK 100  
#elif DLEVEL > 5  
    display( debugptr );  
#else  
    #define STACK 200  
#endif  
```  
  
 İlk `#if` bloğu gösterir iki adet iç içe geçmiş `#if`, `#else`, ve `#endif` yönergeleri. Yönergeleri ilk kümesi yalnızca işlenen `DLEVEL > 5` doğrudur. Aksi takdirde, # sonra deyimleri**başka** işlenir.  
  
 `#elif` Ve `#else` değerine göre dört seçeneklerden birini yapmak için yönergeleri ikinci örnekte kullanılan `DLEVEL`. Sabit `STACK` için 0, 100 veya tanımını bağlı olarak 200 ayarlamak `DLEVEL`. Varsa `DLEVEL` 5 sonra deyimi büyük  
  
```  
#elif DLEVEL > 5  
display(debugptr);  
```  
  
 derlenir ve `STACK` tanımlı değil.  
  
 Koşullu derleme için yaygın bir kullanımdır aynı üstbilgi dosyası birden çok içermeler engellemektir. Sınıflar genellikle üstbilgi dosyalarında tanımlandığı, C++'da, aşağıdaki gibi yapıları birden fazla tanımı önlemek için kullanılabilir:  
  
```  
/*  EXAMPLE.H - Example header file  */  
#if !defined( EXAMPLE_H )  
#define EXAMPLE_H  
  
class Example  
{  
...  
};  
  
#endif // !defined( EXAMPLE_H )  
```  
  
 Önceki kod olup olmadığını denetler. simgesel sabiti `EXAMPLE_H` tanımlanır. Bu durumda, dosya zaten eklenmiştir ve değil işlenmesi. Değil, sabit, `EXAMPLE_H` örnek işaretlemek için tanımlanır. H olarak önceden işlenmiş.  

## <a name="hasinclude"></a>__has_include
**Visual Studio 2017 15.3 ve sonraki sürümleri**: kitaplık üstbilgi eklenmesi için kullanılabilir olup olmadığını belirler:  

```cpp
#ifdef __has_include
#  if __has_include(<filesystem>)
#    include <filesystem>
#    define have_filesystem 1
#  elif __has_include(<experimental/filesystem>)
#    include <experimental/filesystem>
#    define have_filesystem 1
#    define experimental_filesystem
#  else
#    define have_filesystem 0
#  endif
#endif
```
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)