---
title: Yorum (C/C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.comment
- comment_CPP
dev_langs: C++
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4dc4c9036565c2571371c172f61de4948c188f83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comment-cc"></a>comment (C/C++)
Bir yorum kaydı bir nesne dosyası veya yürütülebilir dosyanın yerleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma comment( comment-type [,"commentstring"] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Yorum türü* biri aşağıda açıklanan önceden tanımlanmış tanımlayıcılardır, yorum kaydı türünü belirtir. İsteğe bağlı `commentstring` bazı yorum türleri için ek bilgileri sağlayan bir dize değil. Çünkü `commentstring` bir değişmez dize değişmez değerleri kaçış karakterleri, katıştırılmış tırnak işaretleri göre için tüm kuralları obeys dizesidir (**"**) ve birleştirme.  
  
 **Derleyici**  
 Derleyici adını ve sürüm numarasını nesne dosyasına yerleştirir. Bu açıklama kaydı bağlayıcı tarafından göz ardı edilir. Sağladığınız varsa bir `commentstring` parametresi derleyici bu kayıt türü için bir uyarı oluşturur.  
  
 **exestr**  
 Basamak `commentstring` nesne dosyasına. Bağlantı zaman bu dize yürütülebilir dosya olarak yerleştirilir. Yürütülebilir dosya yüklendiğinde dize belleğe yüklü değil; Ancak, bir programla dosyalarında yazdırılabilir dizeleri bulur bulunabilir. Bir bu açıklama kayıt türü için bir sürüm numarası veya benzer bilgiler bir yürütülebilir dosyada katıştırmak için kullanılır.  
  
 `exestr`kullanım dışıdır ve gelecekteki bir sürümde; kaldırılacak Bağlayıcı yorum kaydı işlemez.  
  
 **LIB**  
 Bir kitaplık arama kaydı nesnesi dosyasına yerleştirir. Bu açıklama türü tarafından eklenmelidir bir `commentstring` adı (ve muhtemelen yolu) aramak için bağlayıcı istediğiniz kitaplığın içeren parametre. Kitaplık adı nesne dosyasındaki varsayılan kitaplık arama kayıtlar izler; Bağlayıcı için bu kitaplığı koşuluyla kitaplığı ile belirtilen değil yalnızca bu komut satırında adlı olarak arar [/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md). Aynı kaynak dosyasına birden çok kitaplık arama kaydı yerleştirebilirsiniz; Bu kaynak dosyasına karşılaşılana aynı sırada nesne dosyasındaki her kayıt görüntülenir.  
  
 Varsayılan kitaplık ve ek kitaplık sırasını önemliyse ile derleme [/Zl](../build/reference/zl-omit-default-library-name.md) anahtar, varsayılan kitaplık adını nesne modülünde yerleştirilen engeller. İkinci bir açıklama pragması sonra sonra eklenen kitaplığı varsayılan kitaplık adını eklemek için kullanılabilir. Bu pragmaları ile listelenen kitaplıkları kaynak kodunda bulunan aynı sırada nesne modülü görünür.  
  
 **Bağlayıcı**  
 Basamak bir [bağlayıcı seçeneği](../build/reference/linker-options.md) nesne dosyasına. Bu açıklama türü için komut satırına geçirme veya geliştirme ortamında belirtme yerine bir bağlayıcı seçeneği belirtmek için kullanabilirsiniz. Örneğin, belirtebilirsiniz / eklenmesi bir simge, zorlama seçeneği içerir:  
  
```  
#pragma comment(linker, "/include:__mySymbol")  
```  
  
 Yalnızca aşağıdaki (*yorum türü*) bağlayıcı tanımlayıcı geçirilecek bağlayıcı seçenekleri kullanılabilir:  
  
-   [/ DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)  
  
-   [/ DIŞARI AKTARMA](../build/reference/export-exports-a-function.md)  
  
-   [/ INCLUDE](../build/reference/include-force-symbol-references.md)  
  
-   [/ MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)  
  
-   [/ MERGE](../build/reference/merge-combine-sections.md)  
  
-   [/ SECTION](../build/reference/section-specify-section-attributes.md)  
  
 **Kullanıcı**  
 Genel bir yorum nesne dosyasına yerleştirir. `commentstring` Parametresi açıklama metni içerir. Bu açıklama kaydı bağlayıcı tarafından göz ardı edilir.  
  
 Aşağıdaki pragma EMAPI için aranacak bağlayıcı neden olur. Bağlama sırasında LIB Kitaplığı'nı tıklatın. Bağlayıcı ilk geçerli çalışma dizininde, ardından LIB ortam değişkeninde belirtilen yolda arar.  
  
```  
#pragma comment( lib, "emapi" )  
```  
  
 Aşağıdaki pragma nesne dosyasında derleyici adını ve sürüm numarasını yerleştirmek derleyici neden olur:  
  
```  
#pragma comment( compiler )  
```  
  
> [!NOTE]
>  Süren yorum bir `commentstring` parametresi, kullanabileceğiniz bir makrosu burada kullandığınız bir dize sabit değeri, herhangi bir yerde koşuluyla bir değişmez dize makrosu genişletir. Ayrıca, dize değişmez değerleri ve dize değişmez değerleri genişletin makroları herhangi bir bileşimini arada kullanabilirsiniz. Örneğin, aşağıdaki ifadeyi kabul edilebilir:  
  
```  
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)