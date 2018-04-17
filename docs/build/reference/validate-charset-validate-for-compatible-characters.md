---
title: -Doğrula-charset (doğrulama uyumlu karakterler) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /validate-charset
- validate-charset
dev_langs:
- C++
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e82b9fd42b636cffd318f6327cc064687334329
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/Validate-Charset (uyumlu karakterler doğrula)
Kaynak dosya metin yalnızca gösterilebilir karakter içerdiğini doğrular UTF-8 olarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/validate-charset[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz **/validate-charset** seçeneği kaynak kodunu yalnızca her iki kaynak karakteri temsil edilebilir karakter ayarlamak ve yürütme karakter kümesi içerdiğini doğrulayın. Belirttiğiniz zaman bu denetimi otomatik olarak etkinleştirilir **/source-charset**, **/execution-charset**, veya **/utf-8** derleyici seçenekleri. Belirterek açıkça bu denetimi devre dışı bırakabilirsiniz **/ doğrula-charset -** seçeneği.  
  
 Varsayılan olarak, Visual Studio kaynak dosya kodlanmış bir Unicode biçiminde, örneğin, UTF-16 veya UTF-8 olup olmadığını belirlemek için bir bayt sırası işareti algılar. Bayt sırası işareti bulunursa, kaynak dosyası kodlanmış geçerli kullanıcı kod sayfası kullanılarak bir kod sayfasını kullanarak belirttiğiniz sürece varsayar **/utf-8** veya **/source-charset** seçeneği. Visual Studio birkaç karakter kodlamaları birini kullanarak C++ kaynak kodu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümesi hakkında daha fazla bilgi için bkz: [karakter kümeleri](../../cpp/character-sets.md) dil belgelerinde. Desteklenen kod sayfası tanımlayıcıları listesini ve karakter kümesi adları için bkz: [kod sayfası tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Visual Studio UTF-8 iç karakter kaynak karakter kümesi ve yürütme karakter kümesi arasında dönüştürme sırasında kodlama olarak kullanır. Yürütme karakter kümesinde bir karakter kaynak dosyasında gösterilemezse, soru işareti UTF-8 dönüştürme değiştirir '?' karakteri. **/Validate-charset** seçeneği bu durumda, bir uyarı bildirmek derleme neden olur.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.  
  
3.  İçinde **Gelişmiş Seçenekler**, ekleme **/validate-charset** seçeneği ve tercih edilen kodlamayı belirtin.  
  
4.  Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/Execution-Charset (ayarlamak yürütme karakter kümesi)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/Source-Charset (ayarlamak kaynak karakter kümesi)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf-8 (Kaynak ve Yürütülebilir karakter kümelerini UTF-8 olarak ayarla)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)