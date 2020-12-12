---
description: 'Şu konuda daha fazla bilgi edinin:/Zc: wchar_t (wchar_t yerel tür)'
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
ms.openlocfilehash: 3dc826bf60c760f45464bcab73dc5fcb79edc3cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178907"
---
# <a name="zcwchar_t-wchar_t-is-native-type"></a>/Zc:wchar_t (wchar_t Yerel Tür)

**`wchar_t`** C++ standardına göre yerleşik bir tür olarak ayrıştırın.

## <a name="syntax"></a>Syntax

> **/Zc: wchar_t**[ **-** ]

## <a name="remarks"></a>Açıklamalar

**/Zc: wchar_t** Ise, **`wchar_t`** C++ olarak derlenen kodda yerleşik integral türü için bir anahtar sözcüktür. **/Zc: wchar_t-** (eksi işareti ile) belirtilirse veya C olarak derlenen kodda, **`wchar_t`** yerleşik bir tür değildir. Bunun yerine, **`wchar_t`** **`typedef`** **`unsigned short`** stddef. h kurallı üstbilgisinde için olarak tanımlanır. (Microsoft uygulama, bunu stddef. h ve diğer standart üstbilgilere dahil olan başka bir üst bilgide tanımlar.)

C++ standardı yerleşik bir tür olmasını gerektirdiğinden **/Zc: wchar_t** önerilmez **`wchar_t`** . Sürümü kullanmak **`typedef`** taşınabilirlik sorunlarına neden olabilir. Visual Studio 'nun önceki sürümlerinden yükseltme yaptıysanız ve kod örtülü olarak ' a dönüştürmeye çalıştığı için derleyici hatası [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) ile karşılaşırsanız **`wchar_t`** **`unsigned short`** , kodu, **/Zc: wchar_t-** ayarını yapmak yerine hatayı giderecek şekilde değiştirmenizi öneririz.

**/Zc: wchar_t** seçeneği varsayılan olarak C++ derlemelerinde açık ve C derlemelerinde yok sayılır. [/Permissive-](permissive-standards-conformance.md) seçeneği **/zc: wchar_t**'yi etkilemez.

Microsoft **`wchar_t`** iki baytlık işaretsiz bir değer olarak uygulanır. Microsoft 'a özgü yerel türe eşlenir **`__wchar_t`** . Hakkında daha fazla bilgi için **`wchar_t`** bkz. [veri türü aralıkları](../../cpp/data-type-ranges.md) ve [temel türler](../../cpp/fundamental-types-cpp.md).

Sürümünü kullanmaya devam eden eski kodla birlikte çalışmak için gereken yeni kod yazarsanız, **`typedef`** **`wchar_t`** **`unsigned short`** **`__wchar_t`** **`wchar_t`** kodunuzun **/Zc: wchar_t** ile derlenen kodla veya kod ile derlenen kodla bağlantılandırabilmesi için hem hem de varyasyonları için aşırı yüklemeler sağlayabilirsiniz. Aksi takdirde, bir tane ve bir ile, **/Zc: wchar_t** etkin olmayan iki farklı kitaplık derlemesi sağlamanız gerekir. Bu durumda bile, eski kodu yeni kodu derlerken kullandığınız derleyicinin aynısını kullanarak oluşturmanızı öneririz. Farklı derleyicilerle derlenmiş ikili dosyaları kesinlikle karıştırmayın.

**/Zc: wchar_t** belirtildiğinde, **\_ wchar \_ t \_ tanımlı** ve **\_ yerel \_ wchar \_ t \_ tanımlanmış** sembolleri tanımlanmıştır. Daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

Kodunuz artık varsayılan olarak açık **wchar_t** olduğundan, KODUNUZ derleyici com genel işlevlerini kullanıyorsa, comsupp. lib ( [Açıklama pragmadan](../../preprocessor/comment-c-cpp.md) veya komut satırından) açık başvuruları comsuppw. lib veya comsuppwd. lib olarak değiştirmenizi öneririz. ( **/Zc: wchar_t** ile derlemeniz gerekiyorsa, comsupp. lib kullanın.) Comdef. h üstbilgi dosyasını eklerseniz, doğru kitaplık sizin için belirtilir. Derleyici COM desteği hakkında daha fazla bilgi için bkz. [DERLEYICI com desteği](../../cpp/compiler-com-support.md).

**`wchar_t`** C kodunu derlerken yerleşik tür desteklenmez. Visual C++ uygunluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **dil** sayfasını seçin.

1. Wchar_t öğesini **yerleşik tür özelliği olarak değerlendirin** .

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
