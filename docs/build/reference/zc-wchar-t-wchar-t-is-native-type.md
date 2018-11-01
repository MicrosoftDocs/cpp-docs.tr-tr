---
title: /Zc:wchar_t (wchar_t Yerel Tür)
ms.date: 03/01/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
ms.openlocfilehash: 13d25a73a0c70789e8b860607e9f222e69ae6d36
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537936"
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t Yerel Tür)

Ayrıştırma `wchar_t` C++ standardına göre yerleşik bir tür olarak.

## <a name="syntax"></a>Sözdizimi

> **/Zc:wchar_t**[**-**]

## <a name="remarks"></a>Açıklamalar

Varsa **/ZC: wchar_t** açıktır, `wchar_t` C++ derlenmiş kod içinde yerleşik bir tamsayı türü için bir anahtar sözcüktür. Varsa **/Zc:wchar_t-** (eksi işaretiyle) C belirtilen, veya kod derlenir `wchar_t` yerleşik bir tür değil. Bunun yerine, `wchar_t` olarak tanımlanan bir `typedef` için `unsigned short` kurallı üstbilgi stddef.h içinde. (Microsoft uygulaması, diğer standart üstbilgi stddef.h tarafından bulunan başka bir üst bilgi de tanımlar.)

Önermeyiz **/Zc:wchar_t-** C++ Standart gerektirdiğinden `wchar_t` yerleşik bir tür olabilir. Kullanarak `typedef` sürümü, taşınabilirlik sorunlarına neden olabilir. Visual C++'ın önceki sürümlerinden yükseltin ve derleyici hatayla karşılaşan [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) kod örtük dönüştürmeye çalıştığı için bir `wchar_t` için `unsigned short`, bunun yerine hatayı gidermek için kodu değiştirmenizi öneririz ayarının **/Zc:wchar_t-**.

**/ZC: wchar_t** seçeneği C++ derlemelerde varsayılan olarak açıktır ve C derlemelerde göz ardı edilir. [/ Permissive-](permissive-standards-conformance.md) seçeneği etkilemez **/ZC: wchar_t**.

Microsoft uygulayan `wchar_t` bir iki baytlık imzalanmamış değer olarak. Microsoft'a özgü yerel türü eşleyen `__wchar_t`. Hakkında daha fazla bilgi için `wchar_t`, bkz: [veri türü aralıkları](../../cpp/data-type-ranges.md) ve [temel türler](../../cpp/fundamental-types-cpp.md).

Hala kullanan eski kod ile birlikte çalışmak için yeni bir kod yazarsanız `typedef` sürümünü `wchar_t`, her ikisi için aşırı yüklemeleri sağlayabilir `unsigned short` ve `__wchar_t` çeşitleri `wchar_t`, böylece kodunuzun ile bağlanabilir derlenmiş kodu **/ZC: wchar_t** ya da onsuz derlenen kod. Aksi takdirde, iki farklı derlemeleri biri diğeri olmadan kitaplığı, sağlamanız gerekecektir **/ZC: wchar_t** etkin. Bu durumda bile, eski kodu yeni kodu derlerken kullandığınız derleyicinin aynısını kullanarak oluşturmanızı öneririz. Farklı derleyicilerle derlenmiş ikili dosyaları kesinlikle karıştırmayın.

Zaman **/ZC: wchar_t** belirtilen  **\_WCHAR\_T\_TANIMLANAN** ve  **\_yerel\_WCHAR\_T\_TANIMLANAN** simgeleri tanımlanır. Daha fazla bilgi için [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

Kodunuzu olduğundan Derleyici COM genel işlevlerini kullanıyorsa **/ZC: wchar_t** üzerinde varsayılan olarak, comsupp.lib açık başvuruların değiştirmenizi öneririz artık (araçtan [pragma açıklama](../../preprocessor/comment-c-cpp.md) veya komut satırı) comsuppw.lib veya comsuppwd.lib. (İle derleme yaparsanız **/Zc:wchar_t-**, comsupp.lib kullanın.) comdef.h üstbilgi dosyasını dahil ederseniz, sizin için doğru kitaplık belirtilir. Derleyici COM desteği hakkında daha fazla bilgi için bkz: [Compiler COM Support](../../cpp/compiler-com-support.md).

`wchar_t` Yerleşik tür C kodunu derlerken desteklenmez. Visual C++ ile uyumluluk sorunları hakkında daha fazla bilgi için bkz. [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **dil** sayfası.

1. Değiştirme **wchar_t yerleşik tür kabul et** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
