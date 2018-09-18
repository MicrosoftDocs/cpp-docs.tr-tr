---
title: Main bağımsız değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98216f9e7354d9699bcaf74430028c88130c97e6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060908"
---
# <a name="arguments-to-main"></a>main Bağımsız Değişkenleri

**ANSI 2.1.2.2.1** Main bağımsız değişkenlerin semantiği

Microsoft C'de, program başlangıcında çağrılan işlev çağrılırsa **ana**. İçin bildirilen prototip yoktur **ana**, ve sıfır, iki veya üç parametreyle tanımlanabilir:

```
int main( void )
int main( int argc, char *argv[] )
int main( int argc, char *argv[], char *envp[] )
```

Ettiği yukarıdaki üçüncü satır **ana** üç parametre kabul eder, ANSI C standardının bir Microsoft uzantısıdır. Üçüncü parametre **envp**, ortam değişkenlerine bir işaretçiler dizisidir. **Envp** dizisi, null işaretçisi tarafından sonlandırılır. Bkz: [main işlevi ve Program yürütme](../c-language/main-function-and-program-execution.md) hakkında daha fazla bilgi için **ana** ve **envp**.

Değişken **argc** hiçbir zaman negatif bir değer içermez.

Dize dizisi ile sona erer **argv [argc]**, null bir işaretçi içerir.

Tüm öğeleri **argv** dizi dizelerin işaretçileridir.

Hiçbir komut satırı bağımsız değişkeni olmadan çağrılan bir program için bir değerini alırsınız **argc**, yürütülebilir dosyanın adını içine yerleştirileceğinden **argv [0]**. (3.0'dan önceki MS-DOS sürümlerinde, yürütülebilir dosya adı kullanılamaz. "C" harfi yerleştirilir **argv [0]**.) Dizeleri tarafından işaret edilen **argv [1]** aracılığıyla **argv [argc - 1]** program parametrelerini temsil eder.

Parametreleri **argc** ve **argv** değiştirilebilir ve program başlangıcı ve program arasındaki depolanan son değerlerini korur.

## <a name="see-also"></a>Ayrıca Bkz.

[Ortam](../c-language/environment.md)