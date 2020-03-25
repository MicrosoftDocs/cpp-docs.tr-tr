---
title: switch Deyimi (C++)
ms.date: 05/06/2019
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 6b09c0eac939f7ca6a12b68ce5deb3fb83ad27c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160820"
---
# <a name="switch-statement-c"></a>switch Deyimi (C++)

İntegral ifadesinin değerine bağlı olarak kodun birden çok bölümü arasında seçim yapılmasına izin verir.

## <a name="syntax"></a>Sözdizimi

```
   switch ( init; expression )
   case constant-expression : statement
   [default  : statement]
```

## <a name="remarks"></a>Açıklamalar

*İfade* bir integral türünde veya tam sayı türüne belirsiz bir dönüştürme olan sınıf türünde olmalıdır. Integral yükseltme, [Standart dönüşümlerde](standard-conversions.md)açıklandığı şekilde gerçekleştirilir.

**Switch** ifadesinin gövdesi, bir dizi **durum** etiketlerinden ve isteğe bağlı bir **varsayılan** etiketten oluşur. **Case** deyimlerinin aynı değere değerlendirebilmesi için iki sabit ifade yoktur. **Varsayılan** etiket yalnızca bir kez görünebilir. Etiketli deyimler sözdizimsel gereksinimler değildir, ancak **Switch** deyimi bu olmadan anlamlı değildir.   Varsayılan deyimin sonunda gelmesi gerekmez; switch ifadesinin gövdesinde herhangi bir yerde görünebilirler. Case veya default etiketi yalnızca switch ifadesinin içinde yer alabilir.

Her bir **Case** etiketindeki *sabit ifade* , *ifade* türüne dönüştürülür ve eşitlik *ifadesi* ile karşılaştırılır. Denetim, **büyük/küçük harf** *ifadesi ifade* *değeriyle eşleşen deyime* geçer. Ortaya çıkan davranış aşağıdaki tabloda gösterilmiştir.

### <a name="switch-statement-behavior"></a>Switch Ifadesinin davranışı

|Koşul|Eylem|
|---------------|------------|
|Dönüştürülen değer yükseltilen denetim ifadesinin ile eşleşiyor.|Denetim, etiketini izleyen deyime aktarılır.|
|Sabitlerin hiçbiri **Case** etiketlerindeki sabitlerle eşleşmez; **varsayılan** bir etiket var.|Denetim **varsayılan** etikete aktarılır.|
|Sabitlerin hiçbiri **Case** etiketlerindeki sabitlerle eşleşmez; **varsayılan** etiket yok.|Denetim, **Switch** ifadesinden sonra ifadeye aktarılır.|

Eşleşen bir ifade bulunursa denetim, sonraki **durum** veya **varsayılan** Etiketler tarafından kesin değildir. [Break](../cpp/break-statement-cpp.md) deyimleri, yürütmeyi durdurmak ve **Switch** ifadesinden sonra denetimi deyime aktarmak için kullanılır. **Break** deyimleri olmadan, eşleşen **Case** etiketinden her bir ifade, **varsayılan değer**de dahil olmak üzere **anahtarın**sonuna kadar yürütülür. Örneğin:

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   char *buffer = "Any character stream";
   int capa, lettera, nota;
   char c;
   capa = lettera = nota = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            capa++;
            break;
         case 'a':
            lettera++;
            break;
         default:
            nota++;
      }
   }
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",
      capa, lettera, (capa + lettera + nota) );
}
```

Yukarıdaki örnekte, `c` büyük bir `A`ise `capa` artırılır. `capa++` sonraki **Break** deyimleri **Switch** ifadesinin gövdesini ve denetimini **while** döngüsüne geçirir. **Break** deyimleri olmadan, `lettera` ve `nota` de artmak üzere yürütme, bir sonraki etiketli ifadeye "düşecek". Benzer bir amaç, `case 'a'`için **Break** ifadesiyle sunulur. `c` küçük harfli bir `a`, `lettera` artırılır ve **Break** ifadesinin **Switch** ifadesinin gövdesini sonlandırılır. `c` bir `a` veya `A`değilse, **varsayılan** ifade yürütülür.

**Visual Studio 2017 ve üzeri:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir) `[[fallthrough]]` özniteliği c++ 17 standardında belirtilir. Bir switch ifadesinde, derleyici için bir ipucu olarak (veya kodu okuyan herhangi bir kişi), bu arada gelen davranışı tasarlanan bir **anahtar** olarak kullanılabilir. Microsoft C++ derleyicisi Şu anda fallthrough davranışa göre uyarı vermiyor, bu nedenle bu özniteliğin derleyici davranışı üzerinde hiçbir etkisi yoktur. Özniteliğin etiketli deyimin içindeki boş bir ifadeye uygulandığını unutmayın; diğer bir deyişle, noktalı virgül gereklidir.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): Switch deyimleri, kapsamı switch ifadesinin bloğu ile sınırlı olan bir değişkeni ortaya çıkarabilir ve başlatabilir:

```cpp
    switch (Gadget gadget(args); auto s = gadget.get_status())
    {
    case status::good:
        gadget.zip();
        break;
    case status::bad:
        throw BadGadget();
    };
```

**Switch** ifadesinin iç bloğu, erişilebilir oldukları sürece başlatmaları olan tanımlar içerebilir; diğer bir deyişle, tüm olası yürütme yolları tarafından atlanmaz. Bu bildirimler kullanılarak tanıtılan adların yerel kapsamı vardır. Örneğin:

```cpp
// switch_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    switch( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    case 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        break;

    case 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        break;

    default:
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        break;
    }
}
```

**Switch** deyimleri iç içe olabilir. Böyle durumlarda, **büyük/küçük harf** veya **varsayılan** Etiketler, bunları kapsayan en yakın **Switch** ifadesiyle ilişkilendirir.

**Microsoft 'a özgü**

Microsoft C, bir **Switch** deyimindeki Case değerlerinin sayısını sınırlamaz. Numara yalnızca kullanılabilir bellekle sınırlıdır. ANSI C, **Switch** ifadesinde en az 257 Case etikete izin verilmesini gerektirir.

Microsoft C için varsayılan değer, Microsoft uzantılarının etkinleştirilme içindir. Bu uzantıları devre dışı bırakmak için [/za](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneğini kullanın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
