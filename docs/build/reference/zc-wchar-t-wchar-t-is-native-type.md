---
title: "/ ZC: wchar_t (wchar_t yerel tür olan) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4970e4aba8bf2d6aebf60f876a4770b18943781
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t Yerel Tür)

Ayrıştırma `wchar_t` C++ Standart göre yerleşik bir tür olarak.

## <a name="syntax"></a>Sözdizimi

> **/Zc:wchar_t**[**-**]

## <a name="remarks"></a>Açıklamalar

Varsa **/ZC: wchar_t** açıktır, `wchar_t` C++ derlenmiş kod yerleşik bir tam sayı türü için bir anahtar sözcüktür. Varsa **/Zc:wchar_t-** (eksi işaretiyle) C belirtildiğinden, veya kod derlenir `wchar_t` yerleşik bir tür değil. Bunun yerine, `wchar_t` olarak tanımlanan bir `typedef` için `unsigned short` kurallı üstbilgi stddef.h içinde. (Microsoft uygulaması, stddef.h tarafından dahil başka bir üstbilgi ve diğer standart üstbilgileri tanımlar.)

Öneririz değil **/Zc:wchar_t-** C++ Standart gerektirdiğinden `wchar_t` yerleşik bir tür olmalıdır. Kullanarak `typedef` sürüm taşınabilirlik sorunlara neden olabilir. Visual C++ önceki sürümlerinden yükseltme ve derleyici hatası karşılaşırsanız [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) kodu örtük dönüştürmeye çalışıyor olduğundan bir `wchar_t` için `unsigned short`, bunun yerine hata düzeltme kodu değiştirmenizi öneririz ayarı **/Zc:wchar_t-**.

**/ZC: wchar_t** seçeneği C++ derlemelerde varsayılan olarak açıktır ve C derlemeleri göz ardı edilir. [/ İzin veren-](permissive-standards-conformance.md) seçeneği etkilemez **/ZC: wchar_t**.

Microsoft uygulayan `wchar_t` iki baytlık imzasız değeri olarak. Microsoft'a özgü yerel tür eşlemeleri `__wchar_t`. Hakkında daha fazla bilgi için `wchar_t`, bkz: [veri türü aralıkları](../../cpp/data-type-ranges.md) ve [temel türleri](../../cpp/fundamental-types-cpp.md).

Hala kullanan eski kod ile birlikte çalışmak için sahip yeni kod yazma `typedef` sürümü `wchar_t`, her ikisi için aşırı sağlayabilir `unsigned short` ve `__wchar_t` varyasyonları `wchar_t`, böylece kodunuzu ile bağlantılı derlenmiş kod **/ZC: wchar_t** veya olmadan derlenmiş kod. Aksi durumda, iki farklı derlemeler biri diğeri olmadan kitaplığı, sağlamak zorunda kalırsınız **/ZC: wchar_t** etkin. Bu durumda bile, eski kodu yeni kodu derlerken kullandığınız derleyicinin aynısını kullanarak oluşturmanızı öneririz. Farklı derleyicilerle derlenmiş ikili dosyaları kesinlikle karıştırmayın.

Zaman **/ZC: wchar_t** belirtilirse,  **\_WCHAR\_T\_TANIMLANAN** ve  **\_yerel\_WCHAR\_T\_TANIMLANAN** simgeleri tanımlanır. Daha fazla bilgi için bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

Çünkü derleyici global COM işlevleri, kodunuzu kullanıyorsa, **/ZC: wchar_t** üzerinde varsayılan olarak, comsupp.lib açık başvurular değiştirmenizi öneririz şimdi (araçtan [pragma açıklama](../../preprocessor/comment-c-cpp.md) veya komut satırı) comsuppw.lib veya comsuppwd.lib. (İle derleme yaparsanız **/Zc:wchar_t-**, comsupp.lib kullanın.) comdef.h üstbilgi dosyasını dahil ederseniz, sizin için doğru kitaplık belirtilir. Derleyici COM desteği hakkında daha fazla bilgi için bkz: [Derleyici COM desteği](../../cpp/compiler-com-support.md).

`wchar_t` C kodu derlerken yerleşik türü desteklenmiyor. Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **dil** sayfası.

1. Değiştirme **wchar_t yerleşik türü olarak kabul** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
