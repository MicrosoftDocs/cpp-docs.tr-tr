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
ms.openlocfilehash: 8136b03d9e54b4d49bcb1417238066bd86bc6b89
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221944"
---
# <a name="switch-statement-c"></a>switch Deyimi (C++)

Kod, tam sayı ifadesinin değerine bağlı olarak birden çok bölüm arasında seçim sağlar.

## <a name="syntax"></a>Sözdizimi

```
   switch ( init; expression )
   case constant-expression : statement
   [default  : statement]
```

## <a name="remarks"></a>Açıklamalar

*İfade* bir tamsayı türü veya bir sınıf türünün var olan bir tamsayı türüne belirsiz dönüştürme olmalıdır. İntegral yükseltme gerçekleştirilir açıklandığı [standart dönüştürmeler](standard-conversions.md).

**Geçiş** oluşan bir dizi deyim gövdesi **çalışması** etiketleri ve isteğe bağlı **varsayılan** etiketi. Hiçbir iki sabit ifadelerde **çalışması** deyimlerindeki aynı değeri. **Varsayılan** etiket yalnızca bir kez görünebilir. Etiketli ifadeler sözdizimsel gereksinimler değildir ancak **geçiş** deyimini bunlar olmadan anlamsız olur.   Varsayılan deyimin sona gelmesi gerekmez; Ayrıca, switch deyimi gövdesinin içinde herhangi bir yerde görünebilir. Bir case veya default etiketi yalnızca switch deyimi içinde bulunabilir.

*Sabit-ifade* her **çalışması** etiket türüne dönüştürülür *ifade* ve ile karşılaştırıldığında *ifade* için Eşitlik. Denetim özelliği deyime geçer **çalışması** *sabit-ifade* değeriyle eşleşen *ifade*. Sonuçta ortaya çıkan davranış aşağıdaki tabloda gösterilmektedir.

### <a name="switch-statement-behavior"></a>Switch deyimi davranışı

|Koşul|Eylem|
|---------------|------------|
|Dönüştürülmüş değeri, yükseltilen denetleme ifadesiyle eşleşir.|Denetim, bu etiketi takiben deyime aktarılır.|
|Sabitlerden hiçbiri sabitlerle eşleşmez **çalışması** etiketler; bir **varsayılan** etiketi görüntülenir.|Denetim aktarılır **varsayılan** etiketi.|
|Sabitlerden hiçbiri sabitlerle eşleşmez **çalışması** etiketler; **varsayılan** etiketi mevcut değil.|Denetim sonraki deyime aktarılır **geçiş** deyimi.|

Eşleşen bir ifade bulunursa denetim sonraki tarafından engellenmez **çalışması** veya **varsayılan** etiketler. [Sonu](../cpp/break-statement-cpp.md) deyimi yürütmeyi durdurmak ve denetimi sonraki deyime aktarmak için kullanılan **geçiş** deyimi. Olmadan bir **sonu** deyimi, eşleşen her deyim **çalışması** sonuna etiket **geçiş**de dahil olmak üzere **varsayılan**, olan yürütülür. Örneğin:

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

Yukarıdaki örnekte, `capa` artırılır `c` bir büyük harf olan `A`. **Sonu** deyiminden sonra `capa++` yürütülmesini sonlandırır **geçiş** deyim gövdesi ve denetim geçtiği **sırada** döngü. Olmadan **sonu** deyimi, yürütme "geçiş" sonraki etiketli deyime, böylece `lettera` ve `nota` de artırılır. Benzer bir amaç tarafından sunulan **sonu** bildirimi `case 'a'`. Varsa `c` küçük harfliyse `a`, `lettera` artırılır ve **sonu** açıklamayı sonlandıran **geçiş** deyim gövdesi. Varsa `c` değil bir `a` veya `A`, **varsayılan** deyimi yürütülür.

**Visual Studio 2017 ve üzeri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) `[[fallthrough]]` özniteliği C ++ 17 standardına belirtildi. İçinde kullanılabilir bir **geçiş** deyimi bu başarısızlığı davranışı ipucu derleyici (veya kodu okuyan herkese) olarak hazırlanmıştır. Microsoft C++ derleyici şu anda değil uyar fallthrough davranışlarına, böylece bu öznitelik derleyici davranışı üzerinde hiçbir etkisi olmaz. Etiketli deyim içinde boş bir deyimi öznitelik uygulandığı dikkat edin. diğer bir deyişle noktalı virgül gereklidir.

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

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)):  Switch deyimi tanıtır ve kapsamı switch ifadesinin blokla sınırlı bir değişken başlatın:

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

İç bloğu, bir **geçiş** deyimi, erişilebilir oldukları sürece Başlatmalarla birlikte tanımlar içerebilir — diğer bir deyişle, tüm olası yürütme yolları tarafından atlanmamıştır. Bu bildirimler kullanılarak bildirilen adlar yerel kapsama sahiptir. Örneğin:

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

A **geçiş** deyimi iç içe geçirilemez. Bu gibi durumlarda **çalışması** veya **varsayılan** etiketlerle ilişkilendirmek en yakın **geçiş** bunları kapsayan deyimi.

**Microsoft'a özgü**

Microsoft C, durum değeri sayısını sınırlamaz bir **geçiş** deyimi. Sayı yalnızca kullanılabilir bellekle sınırlıdır. ANSI C gerektiren en az 257 durum etiketi içinde izin bir **geçiş** deyimi.

Microsoft C için varsayılan Microsoft genişletmelerinin etkinleştirilmiş olduğu. Kullanım [/Za](../build/reference/za-ze-disable-language-extensions.md) bu uzantıları devre dışı bırakma derleyici seçeneği.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)