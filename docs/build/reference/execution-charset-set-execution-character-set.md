---
title: "-yürütme-charset (kümesi yürütme karakter kümesi) | Microsoft Docs"
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
- execution-charset
- /execution-charset
dev_langs: C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64051b4cf54830085a3b35daf6fa8fc3c9af624d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="execution-charset-set-execution-character-set"></a>/Execution-Charset (ayarlamak yürütme karakter kümesi)
Yürütme karakter kümesi için yürütülebilir belirtmenize olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/execution-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>Arguments  
 **IANA_name**  
 IANA tarafından tanımlanan karakter kümesi adı.  
  
 **CPID**  
 Kod sayfası tanımlayıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz **/execution-charset** seçeneği bir yürütme karakter kümesi belirtin. Yürütme karakter kümesi kodlaması tüm adımları ön işleme derleme aşamasına giriş programınızı metni için kullanılan kümesidir. Bu karakter kümesi, bir dize veya karakter değişmez değerleri derlenmiş kod iç gösterimi için kullanılır. Kaynak dosyalarınız temel yürütme karakter kümesinde gösterilebilir olmayan karakterler içeren kullanmak için genişletilmiş yürütme karakter kümesini belirtmek için bu seçeneği ayarlayın. ISO karakter kümesi adı veya bir nokta (.) karakter kümesini belirtmek için bir 3 ile 5 rakamlı ondalık kod sayfası tanımlayıcısı tarafından izlenen ya da IANA kullanabilirsiniz veya. Desteklenen kod sayfası tanımlayıcıları listesini ve karakter kümesi adları için bkz: [kod sayfası tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Varsayılan olarak, Visual Studio kaynak dosya kodlanmış bir Unicode biçiminde, örneğin, UTF-16 veya UTF-8 olup olmadığını belirlemek için bir bayt sırası işareti algılar. Bayt sırası işareti bulunursa, kaynak dosyası kodlanmış geçerli kullanıcı kod sayfası kullanılarak bir karakter kümesi adı veya kod sayfasını kullanarak belirtilmedikçe varsayar **/source-charset** seçeneği veya **/utf-8** seçeneği. Visual Studio birkaç karakter kodlamaları birini kullanarak C++ kaynak kodu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümesi hakkında daha fazla bilgi için bkz: [karakter kümeleri](../../cpp/character-sets2.md) dil belgelerinde.  
  
 Kaynak karakter kümesi ve yürütme karakter kümesi UTF-8'e ayarlamak istiyorsanız kullanabileceğiniz **/utf-8** bir kısayol olarak derleyici seçeneği. Belirtmeye eşdeğer **/source-charset:utf-8 /execution-charset:utf-8** komut satırında. Bunlardan birine seçenekleri de etkinleştirir **/validate-charset** varsayılan seçeneği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.  
  
3.  İçinde **Gelişmiş Seçenekler**, ekleme **/execution-charset** seçeneği ve tercih edilen kodlamayı belirtin.  
  
4.  Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/Source-Charset (ayarlamak kaynak karakter kümesi)](../../build/reference/source-charset-set-source-character-set.md)   
 [/UTF-8 (kaynağı Ayarla ve yürütülebilir karakter kümelerini UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/Validate-Charset (uyumlu karakterler doğrula)](../../build/reference/validate-charset-validate-for-compatible-characters.md)