---
title: -validate-charset (uyumlu karakterler için Doğrula) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- /validate-charset
- validate-charset
dev_langs:
- C++
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adfda3d287bbea6c85ae6d4bcebe009b610d719e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219298"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/ Validate-Charset (uyumlu karakterler için Doğrula)
Kaynak dosyası metin yalnızca gösterilebilir karakterler içerdiğini doğrular UTF-8 olarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/validate-charset[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz **/Validate-Charset** seçeneği kaynak kodu yalnızca her iki kaynak karakteri temsil edilebilir karakter kümesi ve yürütme karakter kümesi içerdiğini doğrulayın. Bu onay, belirttiğiniz zaman otomatik olarak etkinleştirilir **/Source-Charset**, **/Execution-Charset**, veya **/UTF-8** derleyici seçenekleri. Belirterek açıkça bu denetimi devre dışı bırakabilirsiniz **/ validate-charset -** seçeneği.  
  
 Varsayılan olarak, Visual Studio kaynak dosya kodlanmış bir Unicode biçiminde, örneğin, UTF-16 veya UTF-8 olup olmadığını belirlemek için bayt sırası işareti algılar. Bayt sırası işareti yoksa bulunursa, kaynak dosyası kodlanmış geçerli kullanıcı kod sayfası kullanılarak kullanarak bir kod sayfası belirtmiş olduğunuz sürece varsayar **/UTF-8** veya **/Source-Charset** seçeneği. Visual Studio birkaç karakter kodlamaları birini kullanarak C++ kaynak kod kaydetmenize olanak tanır. Kaynak ve yürütme karakter kümeleri hakkında daha fazla bilgi için bkz: [karakter kümeleri](../../cpp/character-sets.md) dil belgelerinde. Karakter kümesi adları ve kod sayfası tanımlayıcıları desteklenen bir listesi için bkz. [kod sayfası tanımlayıcıları](/windows/desktop/Intl/code-page-identifiers).  
  
 Visual Studio, UTF-8 iç karakter kaynak karakter kümesi ve yürütme karakter kümesi arasında dönüştürme sırasında kodlaması olarak kullanır. Kaynak dosyada bir karakter yürütme karakter kümesinde temsil edilemiyorsa UTF-8 dönüştürme bir soru işareti değiştirir '?' karakteri. **/Validate-Charset** seçeneği, bu durumda bir uyarı bildirmek derleme neden olur.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Genişletin **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.  
  
3.  İçinde **Gelişmiş Seçenekler**, ekleme **/Validate-Charset** seçenek ve tercih edilen kodlamayı belirtin.  
  
4.  Seçin **Tamam** yaptığınız değişiklikleri kaydedin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/ Execution-Charset (yürütme karakter kümesini Ayarla)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/ Source-Charset (kaynak karakter kümesini Ayarla)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf-8 (Kaynak ve Yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)