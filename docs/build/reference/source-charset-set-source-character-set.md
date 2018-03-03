---
title: "-Kaynak-charset (kümesi kaynak karakter kümesi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- source-charset
- /source-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4aa81ba41587a183aca921177a62a45229810f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="source-charset-set-source-character-set"></a>/Source-Charset (ayarlamak kaynak karakter kümesi)
Kaynak karakter kümesi için yürütülebilir belirtmenize olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/source-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>Arguments  
 **IANA_name**  
 IANA tarafından tanımlanan karakter kümesi adı.  
  
 **CPID**  
 Ondalık sayı olarak kod sayfası tanımlayıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz **/source-charset** bir genişletilmiş kaynak karakter kümesi Kaynak dosyalarınız temel kaynak karakter kümesinde temsil karakterler kullanırsanız kullanılacağını belirtmek için seçeneği. Kaynak karakter derleme önce önişlem aşamaları giriş olarak kullanılan iç gösterimi içine programınızın kaynak metni bilgilerini yorumlamak için kullanılacak kodlama kümesidir. İç temsili sonra yürütülebilir dosya dize ve karakter değerlerini depolamak için yürütme karakter kümesi dönüştürülür. ISO karakter kümesi adı veya bir nokta (.) karakter kümesini belirtmek için bir 3 ile 5 rakamlı ondalık kod sayfası tanımlayıcısı tarafından izlenen ya da IANA kullanabilirsiniz veya. Desteklenen kod sayfası tanımlayıcıları listesini ve karakter kümesi adları için bkz: [kod sayfası tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Varsayılan olarak, Visual Studio kaynak dosya kodlanmış bir Unicode biçiminde, örneğin, UTF-16 veya UTF-8 olup olmadığını belirlemek için bir bayt sırası işareti algılar. Bayt sırası işareti bulunursa, kaynak dosyası kodlanmış geçerli kullanıcı kod sayfası kullanılarak bir karakter kümesi adı veya kod sayfasını kullanarak belirtmediğiniz sürece varsayar **/source-charset** seçeneği. Visual Studio birkaç karakter kodlamaları birini kullanarak C++ kaynak kodu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümesi hakkında daha fazla bilgi için bkz: [karakter kümeleri](../../cpp/character-sets2.md) dil belgelerinde.  
  
 Sağladığınız kaynak karakter kümesi 7 bitlik ASCII karakter kümesi içinde aynı kod noktaları eşlenmesi gerekir veya birçok derleme hataları büyük bir olasılıkla izleyin. Kaynak karakter kümesi de eşlenebilir genişletilmiş Unicode karakter UTF-8 ile encodable kümesi olmalıdır. UTF-8'de encodable olmayan karakterler bir uygulamaya özel yedek temsil edilir. Microsoft derleyici için bu karakterler soru işareti kullanır.  
  
 Kaynak karakter kümesi ve yürütme karakter kümesi UTF-8'e ayarlamak istiyorsanız kullanabileceğiniz **/utf-8** bir kısayol olarak derleyici seçeneği. Belirtmeye eşdeğer **/source-charset:utf-8 /execution-charset:utf-8** komut satırında. Bunlardan birine seçenekleri de etkinleştirir **/validate-charset** varsayılan seçeneği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.  
  
3.  İçinde **Gelişmiş Seçenekler**, ekleme **/source-charset** seçeneği ve tercih edilen kodlamayı belirtin.  
  
4.  Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/Execution-Charset (ayarlamak yürütme karakter kümesi)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/UTF-8 (kaynağı Ayarla ve yürütülebilir karakter kümelerini UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/Validate-Charset (uyumlu karakterler doğrula)](../../build/reference/validate-charset-validate-for-compatible-characters.md)