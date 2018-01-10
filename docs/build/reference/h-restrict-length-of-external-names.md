---
title: "-H (Dış adların uzunluğunu kısıtla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /h
dev_langs: C++
helpviewer_keywords:
- public name length
- /H compiler option [C++]
- H compiler option [C++]
- external names
- -H compiler option [C++]
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d5e862eb8e45d1f2558592c0bb54c1adb9305f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="h-restrict-length-of-external-names"></a>/H (Dış Adların Uzunluğunu Kısıtla)
Kullanım dışı. Dış adların uzunluğunu kısıtlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Hnumber  
```  
  
## <a name="arguments"></a>Arguments  
 `number`  
 Dış adların bir programı izin verilen uzunluk üst sınırını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, dış (Genel) adların uzunluğunu 2,047 karakterdir. Bu, C ve C++ programları için geçerlidir. Kullanarak **/H** yalnızca tanımlayıcıları için izin verilen uzunluk sınırını azaltın, artırmak değil. Arasında bir boşluk **/H** ve `number` isteğe bağlıdır.  
  
 Dış adlar daha uzun bir program içeriyorsa, `number`, fazladan karakterler göz ardı edilir. Bir program olmadan derleme yaparsanız **/H** ve bir tanımlayıcı birden fazla 2,047 karakterler içeriyorsa, derleyici oluşturacak [önemli hata C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md).  
  
 Tüm derleyici oluşturulan başında alt çizgi (_) uzunluk sınırını içerir veya at işareti (@). Bu karakterleri tanımlayıcı parçası olan ve önemli bir konum gerçekleştirin.  
  
-   Derleyici değiştiren adlarının önünde alt çizgi (_) ekler `__cdecl` (varsayılan) ve `__stdcall` işaretini çağırma kuralları ve başında (@) değiştiren adlarına `__fastcall` çağırma.  
  
-   Bağımsız değişkeni boyut bilgileri derleyici değiştiren adları ekler `__fastcall` ve `__stdcall` çağırma kuralları ve C++ adlarına türü bilgilerini ekler.  
  
 Fark edebilirsiniz **/H** yararlıdır:  
  
-   Karışık dil veya taşınabilir program oluşturduğunuzda.  
  
-   Dış tanımlayıcıları uzunluğu sınırları zorunlu tuttukları araçları kullandığınızda.  
  
-   Hata ayıklama derlemede sembolleri kullanma alan miktarını sınırlamak istediğinizde.  
  
 Aşağıdaki örnekte gösterildiği nasıl **/H** tanımlayıcısı uzunlukları çok sınırlıysa gerçekte hatalara neden olabilir:  
  
```cpp  
// compiler_option_H.cpp  
// compile with: /H5  
// processor: x86  
// LNK2005 expected  
void func1(void);  
void func2(void);  
  
int main() { func1(); }  
  
void func1(void) {}  
void func2(void) {}  
```  
  
 Ayrıca kullanırken dikkatli olmalıdır **/H** önceden tanımlanmış derleyici tanımlayıcıları nedeniyle seçeneği. En fazla tanımlayıcı uzunluğu çok kısa ise, belirli önceden tanımlanmış tanımlayıcılardır çözümlenmemiş yanı sıra belirli kitaplığı işlev çağrılarını olacaktır. Örneğin, varsa `printf` işlevi kullanılır ve seçeneği **/H5** derleme zamanında simgenin belirtilen **_prin** başvurmak için oluşturulan `printf`, ve bu bulunamayacaktır Kitaplığı'nda.  
  
 Kullanımı **/H** uyumlu değil. [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).  
  
 **/H** bu yana Visual Studio 2005 seçeneği kullanım dışı; en fazla uzunluk sınırı artar ve **/H** artık gerekli değildir. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** içinde [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)