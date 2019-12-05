---
title: 'main: Program Başlatma'
ms.date: 11/04/2016
f1_keywords:
- vc.main.startup
- _tmain
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
ms.openlocfilehash: 29e1b77c2e36c66e4e6fc4ec30a73af4d57654a0
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857443"
---
# <a name="main-program-startup"></a>main: Program Başlatma

**Main** adlı özel bir işlev, tüm C ve C++ programlar için yürütmenin başlangıç noktasıdır. Unicode programlama modeline uyan bir kod yazıyorsanız, **Main**'in geniş karakterli sürümü olan `wmain`kullanabilirsiniz.

**Main** işlevi derleyici tarafından önceden tanımlı değil. Program metninde sağlanması gerekir.

**Main** için bildirim söz dizimi

```cpp
int main();
```

ya da, isteğe bağlı olarak,

```cpp
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft 'a özgü**

`wmain` için bildirim sözdizimi şöyledir:

```cpp
int wmain( );
```

ya da, isteğe bağlı olarak,

```cpp
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

Ayrıca, Tchar. h içinde tanımlanan `_tmain`de kullanabilirsiniz. _UNICODE tanımlanmadığı müddetçe `_tmain` **ana** olarak çözümlenir. Bu durumda, `_tmain` `wmain`çözümlenmektedir.

Alternatif olarak, **Main** ve `wmain` işlevleri, **void** döndürüyor (dönüş değeri yok) olarak da bildirilemez. **Main** veya `wmain` **void**döndürüyor olarak bildirirseniz, bir [dönüş](../cpp/return-statement-in-program-termination-cpp.md) bildirimi kullanarak üst işleme veya işletim sistemine çıkış kodu döndüremez. **Main** veya `wmain` **void**olarak bildirildiği zaman çıkış kodu döndürmek için, [Exit](../cpp/exit-function.md) işlevini kullanmanız gerekir.

**SON Microsoft 'a özgü**

`argc` ve `argv` türleri, dil tarafından tanımlanır. `argc`, `argv`ve `envp` adları geleneksel, ancak derleyici için gerekli değildir. Daha fazla bilgi ve örnek için bkz. [bağımsız değişken tanımları](../cpp/argument-definitions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[main Yerine wmain Kullanma](../cpp/using-wmain-instead-of-main.md)<br/>
[main İşlevi Kısıtlamaları](../cpp/main-function-restrictions.md)<br/>
[C++ Komut Satırı Bağımsız Değişkenlerini Ayrıştırma](../cpp/parsing-cpp-command-line-arguments.md)
