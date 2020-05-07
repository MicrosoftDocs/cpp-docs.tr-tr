---
title: main Bağımsız Değişkenleri
ms.date: 11/04/2016
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
ms.openlocfilehash: 918be9d281f1cb12c27c6c2f5dd834e4af137179
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313564"
---
# <a name="arguments-to-main"></a>main Bağımsız Değişkenleri

**ANSI 2.1.2.2.1** Bağımsız değişkenlerin anlamını ana

Microsoft C 'de, program başlangıcında çağrılan işlev **Main**olarak adlandırılır. **Main**için bildirilmemiş bir prototip yoktur ve sıfır, iki veya üç parametreyle tanımlanabilir:

```
int main( void )
int main( int argc, char *argv[] )
int main( int argc, char *argv[], char *envp[] )
```

Yukarıdaki üçüncü satır, **Main** 'in üç parametre kabul ettığı, ANSI C standardına yönelik bir Microsoft uzantısıdır. Bu üçüncü parametre olan **envp**, ortam değişkenlerine yönelik işaretçilerin bir dizisidir. **Envp** dizisi bir null işaretçi tarafından sonlandırılır. **Main** ve **envp**hakkında daha fazla bilgi Için bkz. [Main işlevi ve program yürütme](../c-language/main-function-and-program-execution.md) .

**Argc** değişkeni hiçbir şekilde negatif bir değer bulundurmayın.

Dizelerin dizisi, null bir işaretçi içeren **argv [argc]** ile biter.

**Argv** dizisinin tüm öğeleri dizelerin işaretçileridir.

Çalıştırılabilir dosyanın adı **argv [0]** içine yerleştirildiğinden, komut satırı bağımsız değişkenleri olmadan çağrılan program, **argc**için bir değer alır. (3.0'dan önceki MS-DOS sürümlerinde, yürütülebilir dosya adı kullanılamaz. "C" harfi **argv [0]** içine yerleştirildi.) Argv [ **1]** ile **argv [argc-1]** arasındaki işaret edilen dizeler program parametrelerini temsil eder.

**Argc** ve **argv** parametreleri değiştirilebilir ve program başlatma ve program sonlandırma arasında son saklanan değerleri korur.

## <a name="see-also"></a>Ayrıca bkz.

[Ortam](../c-language/environment.md)
