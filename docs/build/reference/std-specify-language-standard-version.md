---
title: "-std (dil standart sürümünü belirtin) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
dev_langs: C++
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d5397af7c83865d833b9a57a9baaf380aa207ca8
ms.sourcegitcommit: 78f3f8208d49b7c1d87f4240f4a1496b7c29333e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/17/2017
---
# <a name="std-specify-language-standard-version"></a>/Std (dil standart sürümünü belirtin)

C++ dil özellikleri standart C++ dili belirtilen sürümünden etkinleştir desteklenir.

## <a name="syntax"></a>Sözdizimi

> /Std: [c ++ 14 | c ++ 17 | c ++ son]

## <a name="remarks"></a>Açıklamalar

**/Std** seçeneği sürüme özgü ISO C++ programlama dili standart özelliklerine kodunuzu derleme sırasında etkin denetlemek için kullanılır. Bu seçenek, belirli bir dil sürümü için uygun mevcut kodunuzu standart kesilebilir belirli özellikler için destek yeni dil ve Kitaplığı devre dışı bırakmanıza olanak tanır. Varsayılan olarak, **/Std: c ++ 14** belirtilirse, hangi devre dışı bırakır dil ve standart kitaplığı özellikleri C++ dili sonraki sürümlerini standart bulundu. Kullanım **/Std: c ++ 17** C ++ 17 standart özgü özellikler ve davranışı etkinleştirmek için. En son desteklenen derleyicisi ve standart kitaplığı özellikleri açıkça etkinleştirmek için **/Std: c ++ Son**.

Varsayılan **/Std: c ++ 14** seçeneği Visual C++ derleyicisi tarafından uygulanan C ++ 14 özellikleri kümesi sağlar. Bu seçenek derleyicisi ve standart kitaplığı desteği değiştirilen özellikler için veya yeni dil standart Visual C++ Derleyici önceki sürümlerde zaten uygulanmış bazı C ++ 17 özellikleri hariç olmak üzere daha yeni sürümlerinde devre dışı bırakır. Visual Studio 2015 güncelleştirme 2'ten itibaren kullanılabilir özellikler üzerinde bağımlılıkları zaten gerçekleştirmişsiniz kullanıcılar için önemli değişiklikler önlemek için bu özellikler ne zaman etkin kalmaya devam **/Std: c ++ 14** seçeneği belirtildiğinde:

- [Otomatik braced-init-listeleriyle için kurallar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [TypeName şablon şablon parametrelerinde](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [Trigrafları kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [Ad alanları ve numaralandırmalar için öznitelikler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [U8 karakter değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

Ek bilgi için hangi C ++ 14 ve C ++ 17 özellikleri ne zaman etkin **/Std: c ++ 14** olduğu belirtilen notları bkz [Visual C++ dili uygunluk](../../visual-cpp-language-conformance.md).
  
**/Std: c ++ 17** seçeneği tam Visual C++ derleyicisi tarafından uygulanan C ++ 17 özellikler kümesi sağlar. Bu seçenek, C ++ 17 sonra derleyicisi ve standart kitaplığı desteği değiştirilen özellikler için veya yeni C++ standart çalışma taslak ve hatasını güncelleştirmeleri sürümlerinde devre dışı bırakır.  
  
**/Std: c ++ Son** seçeneği en izlemek için Visual C++ tarafından uygulanan C++ dili ve kitaplık özellikler kümesi sağlar C ++ 17 dahil edilmeyen yeni C ++ 20 çalışma taslak ve hatasını güncelleştirmelerini C++ standart. Post almak için bu anahtarı kullanın-C ++ 17 dil özellikleri derleyicisi ve standart kitaplığı tarafından desteklenir. Desteklenen Dil ve kitaplık özellikleri listesi için bkz: [Visual c++ yenilikleri](../../what-s-new-for-visual-cpp-in-visual-studio.md). **/Std: c ++ Son** seçeneği tarafından korumalı özellikleri etkinleştirmemeniz **/ Deneysel** geçin.  
  
**/Std** yürürlükte C++ derleme sırasında seçeneğini kullanarak algılanan [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md) önişlemci makrosu. Daha fazla bilgi için bkz: [Önişlemci makroları](../../preprocessor/predefined-macros.md).

**/Std: c ++ 14** ve **/Std: c ++ Son** seçeneklerdir Visual C++ 2015 güncelleştirme 3'te başlayarak bulunabilir. **/Std: c ++ 17** Visual C++ 2017 sürüm 15.3 başında bir seçenektir. Bazı C ++ 17 yukarıdaki standart belirtildiği gibi davranış etkin **/Std: c ++ 14** seçeneği, ancak diğer tüm C ++ 17 özellikleri etkindir **/Std: c ++ 17**.
  
> [!NOTE]
> Visual C++ Derleyici sürümü veya güncelleştirme düzeyine bağlı olarak, belirli C ++ 14 veya C ++ 17 özellikleri değil tam olarak uygulanabilir veya tam olarak belirttiğiniz zaman uyumluluğunu **/Std: c ++ 14** veya **/Std: c ++ 17** seçenekleri. Örneğin, Visual C++ 2017 RTM Derleyici tam olarak C ++ 14-uyumluluğunu desteklemez `constexpr`, ifade SFINAE ya da 2 aşamalı ad araması. C++ dili uyumluluğu Visual C++ sürümü tarafından genel bakış için bkz: [Visual C++ dili uygunluk](../../visual-cpp-language-conformance.md). 
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **yapılandırma özellikleri**, **C/C++**, **dil**.  
  
3.  İçinde **C++ dili standart**, aşağı açılan denetiminden desteği, ardından seçin dil standart seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca bkz.  
  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
