---
title: -yürütme-charset (yürütme karakter kümesini Ayarla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- execution-charset
- /execution-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02f3e4273e9fc4064b26c6e32d708c4e6d586ae1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212678"
---
# <a name="execution-charset-set-execution-character-set"></a>/ Execution-Charset (yürütme karakter kümesini Ayarla)
Yürütme karakter için yürütülebilir dosya kümesi belirtmenize olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/execution-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>Arguments  
 **IANA_name**  
 IANA tarafından tanımlanan karakter kümesinin adı.  
  
 **CPID**  
 Kod sayfası tanımlayıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz **/Execution-Charset** bir yürütme karakter kümesi belirtmek için seçeneği. Yürütme karakter kümesi, programınızın tüm adımları ön işleme derleme aşaması için giriş metni için kullanılan kodlamayı kümesidir. Bu karakter kümesi, bir dize veya karakter değişmez değerleri derlenmiş kodda iç gösterimi için kullanılır. Kaynak dosyalarınız temel yürütme karakter kümesinde temsil edilebilir olmayan karakterler içeren kullanmak için genişletilmiş yürütme karakter kümesi belirtmek için bu seçeneği ayarlayın. Ya da IANA kullanabilir veya ISO karakter kümesinin adı veya bir nokta (.) karakter kümesini belirtmek için bir 3-5 basamaklı ondalık kod sayfası tanımlayıcısı tarafından takip. Karakter kümesi adları ve kod sayfası tanımlayıcıları desteklenen bir listesi için bkz. [kod sayfası tanımlayıcıları](/windows/desktop/Intl/code-page-identifiers).  
  
 Varsayılan olarak, Visual Studio kaynak dosya kodlanmış bir Unicode biçiminde, örneğin, UTF-16 veya UTF-8 olup olmadığını belirlemek için bayt sırası işareti algılar. Bayt sırası işareti yoksa bulunursa, kaynak dosyası kodlanmış geçerli kullanıcı kod sayfası kullanılarak bir karakter kümesi adı veya kod sayfasını kullanarak belirtilmedikçe varsayar **/Source-Charset** seçeneği veya **/UTF-8** seçeneği. Visual Studio birkaç karakter kodlamaları birini kullanarak C++ kaynak kod kaydetmenize olanak tanır. Kaynak ve yürütme karakter kümeleri hakkında daha fazla bilgi için bkz: [karakter kümeleri](../../cpp/character-sets.md) dil belgelerinde.  
  
 Kaynak karakter kümesi hem yürütme karakter kümesini UTF-8'e ayarlamak istiyorsanız, kullanabileceğiniz **/UTF-8** kısayol olarak derleyici seçeneği. Belirtmeye eşdeğerdir **/source-charset:utf-8 /execution-charset:utf-8** komut satırında. Bunlardan birine seçenekleri de etkinleştirir **/Validate-Charset** varsayılan seçeneği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Genişletin **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.  
  
3.  İçinde **Gelişmiş Seçenekler**, ekleme **/Execution-Charset** seçenek ve tercih edilen kodlamayı belirtin.  
  
4.  Seçin **Tamam** yaptığınız değişiklikleri kaydedin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/ Source-Charset (kaynak karakter kümesini Ayarla)](../../build/reference/source-charset-set-source-character-set.md)   
 [/ UTF-8 (kaynak ayarlayın ve yürütülebilir karakter kümelerini UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/validate-charset (Uyumlu karakterler için doğrula)](../../build/reference/validate-charset-validate-for-compatible-characters.md)