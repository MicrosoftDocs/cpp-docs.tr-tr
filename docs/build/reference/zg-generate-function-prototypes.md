---
description: Daha fazla bilgi edinin:/zg (Işlev prototipleri üret)
title: /Zg (İşlev Prototipleri Üret)
ms.date: 11/04/2016
f1_keywords:
- /zg
helpviewer_keywords:
- Zg compiler option [C++]
- /Zg compiler option [C++]
- function prototypes, generate function prototypes compiler option
- -Zg compiler option [C++]
- generate function prototypes compiler option
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
ms.openlocfilehash: ee0bed48f15acae867d344a60a6d42f3b17c7e85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178881"
---
# <a name="zg-generate-function-prototypes"></a>/Zg (İşlev Prototipleri Üret)

Kaldırıldı. Kaynak dosyada tanımlanan her işlev için bir işlev prototipi oluşturur, ancak kaynak dosyayı derlemez.

## <a name="syntax"></a>Syntax

```
/Zg
```

## <a name="remarks"></a>Açıklamalar

Bu derleyici seçeneği artık kullanılamıyor. Visual Studio 2015 ' de kaldırılmıştır. Bu sayfa, Visual Studio 'nun eski sürümlerinin kullanıcıları için kalır.

İşlev prototipi, işlev dönüş türünü ve bir bağımsız değişken türü listesini içerir. Bağımsız değişken türü listesi, işlevin biçimsel parametre türlerinden oluşturulur. Kaynak dosyada zaten bulunan tüm işlev prototipleri yoksayıldı.

Prototiptürlerin listesi standart çıktıya yazılır. Bu listeyi, bir işlevin gerçek bağımsız değişkenlerinin ve biçimsel parametrelerinin uyumlu olduğunu doğrulamak için yararlı bulabilirsiniz. Standart çıktıyı bir dosyaya yönlendirerek listeyi kaydedebilirsiniz. Ardından, işlev prototipleri listesini kaynak dosyanızın bir parçası yapmak için **#include** kullanabilirsiniz. Bunun yapılması derleyicinin bağımsız değişken tür denetimi gerçekleştirmesine neden olur.

**/Zg** seçeneğini kullanırsanız ve programınız struct, Enum veya Union türü (veya bu tür işaretçiler) içeren biçimsel parametreler içeriyorsa, her bir yapının, numaralandırmanın veya birleşim türünün bildirimi bir etikete (ad) sahip olmalıdır. Aşağıdaki örnekte, etiket adı ' dir `MyStruct` .

```C
// Zg_compiler_option.c
// compile with: /Zg
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```

**/Zg** seçeneği visual Studio 2005 ' de kullanımdan kaldırılmıştır ve visual Studio 2015 ' de kaldırılmıştır. MSVC derleyicisi, daha eski, C stili kod için desteği kaldırdı. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, bkz. [kategoriye göre listelenen derleyici seçeneklerinde](compiler-options-listed-by-category.md) **kullanım dışı ve kaldırılmış derleyici seçenekleri** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
