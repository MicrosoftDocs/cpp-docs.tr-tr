---
title: "-utf-8 (kaynağı Ayarla ve UTF-8 kümelerine karakter yürütülebilir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /utf-8
dev_langs: C++
helpviewer_keywords: /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d1f5d48006fff5166fff6fa559323a96997c9ed4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/UTF-8 (kaynağı Ayarla ve yürütülebilir karakter kümelerini UTF-8)
Kaynak karakter kümesi hem UTF-8 olarak yürütme karakter kümesi belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/utf-8  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz **/utf-8** UTF-8 ile kodlanmış gibi hem kaynak hem de yürütme karakter kümesi belirtme seçeneği. Belirtmeye eşdeğer **/source-charset:utf-8 /execution-charset:utf-8** komut satırında. Bunlardan birine seçenekleri de etkinleştirir **/validate-charset** varsayılan seçeneği. Desteklenen kod sayfası tanımlayıcıları listesini ve karakter kümesi adları için bkz: [kod sayfası tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Varsayılan olarak, Visual Studio kaynak dosya kodlanmış bir Unicode biçiminde, örneğin, UTF-16 veya UTF-8 olup olmadığını belirlemek için bir bayt sırası işareti algılar. Bayt sırası işareti bulunursa, kaynak dosyası kodlanmış geçerli kullanıcı kod sayfası kullanılarak bir kod sayfasını kullanarak belirttiğiniz sürece varsayar **/utf-8** veya **/source-charset** seçeneği. Visual Studio birkaç karakter kodlamaları birini kullanarak C++ kaynak kodu kaydetmenizi sağlar. Kaynak ve yürütme karakter kümesi hakkında daha fazla bilgi için bkz: [karakter kümeleri](../../cpp/character-sets2.md) dil belgelerinde.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri**, **C/C++**, **komut satırı** klasör.  
  
3.  İçinde **Gelişmiş Seçenekler**, ekleme **/utf-8** seçeneği ve tercih edilen kodlamayı belirtin.  
  
4.  Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/Execution-Charset (ayarlamak yürütme karakter kümesi)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/Source-Charset (ayarlamak kaynak karakter kümesi)](../../build/reference/source-charset-set-source-character-set.md)   
 [/Validate-Charset (uyumlu karakterler doğrula)](../../build/reference/validate-charset-validate-for-compatible-characters.md)