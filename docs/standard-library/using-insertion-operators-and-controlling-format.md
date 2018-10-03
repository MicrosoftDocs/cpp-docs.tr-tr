---
title: Ekleme işleçlerini kullanma ve biçimi denetleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- insertion operators
ms.assetid: cdefe986-6548-4cd1-8a67-b431d7d36a1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60f82332f9dd0fa6d6e64beb2a5d793784471a1f
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234605"
---
# <a name="using-insertion-operators-and-controlling-format"></a>Ekleme İşleçlerini Kullanma ve Biçimi Denetleme

Bu konu nasıl biçimini denetlemek ve kendi ekleme işleçlerini oluşturma işlemini gösterir. Ekleme (**<<**) tüm standart C++ veri türleri için programlanmış, işleci, bir çıkış akışı nesnesine bayt gönderir. Ekleme işleçlerini ", tamsayı bağımsız değişkeni varsayılan biçimi değiştirme öğeler önceden tanımlanmış manipülatörleri ile" çalışır.

Aşağıdaki seçenekler biçimiyle denetleyebilirsiniz:

- [Çıkış genişliği](#vclrfoutputwidthanchor3)

- [Hizalama](#vclrfalignmentanchor4)

- [Duyarlık](#vclrfprecisionanchor5)

- [sayı tabanı](#vclrfradixanchor6)

## <a name="vclrfoutputwidthanchor3"></a> Çıkış genişliği

Çıkış hizalamak için her öğe için çıkış genişliğini yerleştirerek belirttiğiniz `setw` işleyici stream'de veya çağırarak `width` üye işlevi. Bu örnekte sağ-geniş bir sütun en az 10 karakter değerleri hizalanır:

```cpp
// output_width.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   for( int i = 0; i < 4; i++ )
   {
      cout.width(10);
      cout << values[i] << '\n';
   }
}
```

```Output
      1.23
     35.36
     653.7
   4358.24
```

Baştaki boşluk geniş 10'dan az karakter herhangi bir değere eklenir.

Bir alan paneli kullanın `fill` belirtilen genişlik sahip alanlar için doldurma karakteri değerini ayarlayan üye işlevi. Boş bir varsayılandır. Bir yıldız işareti ile sayı sütununun paneli için önceki değişiklik **için** gibi döngü:

```cpp
for (int i = 0; i <4; i++)
{
    cout.width(10);
    cout.fill('*');
    cout << values[i] << endl;
}
```

`endl` İşleyici yerini alan yeni satır karakteri (`'\n'`). Çıktı şuna benzer:

```Output
******1.23
*****35.36
*****653.7
***4358.24
```

Aynı satırda genişliği veri öğelerini belirtmek için kullanın `setw` işleyici:

```cpp
// setw.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   char *names[] = { "Zoot", "Jimmy", "Al", "Stan" };
   for( int i = 0; i < 4; i++ )
      cout << setw( 7 )  << names[i]
           << setw( 10 ) << values[i] << endl;
}
```

`width` Üye işlevi içinde bildirilen \<iostream >. Kullanırsanız `setw` veya diğer herhangi bir işleyici bağımsız değişkenlerle eklemelisiniz \<iomanip >. Çıktıda bir alan genişliği 6 ve bir alan genişliği 10 tamsayılar dizeleri yazdırılır:

```Output
   Zoot      1.23
  Jimmy     35.36
     Al     653.7
   Stan   4358.24
```

Ne `setw` ya da `width` değerleri keser. Biçimlendirilmiş çıkış genişliği değerin tamamını yazdırır, akışın duyarlık ayarı tabi aşıyor. Her ikisi de `setw` ve `width` yalnızca şu alan etkiler. Alan genişliği döner varsayılan davranışını (gerekli genişlik) sonra bir alan yazdırılır. Ancak, değiştirilmiş kadar diğer akış biçimlendirme seçeneklerini yürürlükte kalır.

## <a name="vclrfalignmentanchor4"></a> Hizalama

Sağa hizalı metin varsayılana çıkış akışı. Önceki örnekte adları Sola Hizala ve sayıları sağa hizala değiştirin **için** gibi döngü:

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6) << names[i]
         << resetiosflags(ios::left)
         << setw(10) << values[i] << endl;
```

Çıktı şuna benzer:

```Output
Zoot        1.23
Jimmy      35.36
Al         653.7
Stan     4358.24
```

Left-align bayrağı kullanılarak ayarlanan [setiosflags](../standard-library/iomanip-functions.md#setiosflags) işleyici ile `left` Numaralandırıcı. Bu Numaralandırıcının tanımlanan [ios](../standard-library/basic-ios-class.md) sınıfı, başvuru eklemeniz gerekir, böylece **ios::** önek. [Resetiosflags](../standard-library/iomanip-functions.md#resetiosflags) işleyici left-align bayrağı devre dışı bırakır. Farklı `width` ve `setw`, etkisini `setiosflags` ve `resetiosflags` kalıcıdır.

## <a name="vclrfprecisionanchor5"></a> Duyarlık

Kayan nokta duyarlığını için varsayılan değer altıysa. Örneğin, 3466.9768 sayı 3466.98 yazdırır. Bu değer yazdırma şeklini değiştirmek için kullanın [setprecision](../standard-library/iomanip-functions.md#setprecision) işleyici. İşleyici iki bayraklara: [sabit](../standard-library/ios-functions.md#fixed) ve [bilimsel](../standard-library/ios-functions.md#scientific). Varsa [sabit](../standard-library/ios-functions.md#fixed) ayarlandığında, 3466.976800 olarak sayı yazdırır. Varsa `scientific` , bunu yazdırır 3.4669773 + 003 ayarlanmış.

Gösterilen kayan noktalı sayıların görüntülenecek [hizalama](#vclrfalignmentanchor4) bir önemli rakam ile değiştirin **için** gibi döngü:

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6)
         << names[i]
         << resetiosflags(ios::left)
         << setw(10)
         << setprecision(1)
         << values[i]
         << endl;
```

Bu liste program yazdırır:

```Output
Zoot          1
Jimmy     4e+01
Al        7e+02
Stan      4e+03
```

Bilimsel gösterim ortadan kaldırmak için önce bu bildirimi Ekle **için** döngü:

```cpp
cout << setiosflags(ios::fixed);
```

Sabit gösterimiyle program ondalık ayırıcıdan sonra bir rakamla yazdırır.

```Output
Zoot         1.2
Jimmy       35.4
Al         653.7
Stan      4358.2
```

Değiştirirseniz `ios::fixed` bayrak `ios::scientific`, programın bu yazdırır:

```cpp
Zoot    1.2e+00
Jimmy   3.5e+01
Al      6.5e+02
Stan    4.4e+03
```

Yeniden program bir sayı ondalık ayırıcıdan sonra yazdırır. Ya da `ios::fixed` veya `ios::scientific` , duyarlık değeri ondalık ayırıcıdan sonra basamak sayısını belirler, ayarlanmış. Hiçbiri bayrağı ayarlandıysa, duyarlık değeri anlamlı basamak sayısını belirler. `resetiosflags` İşleyici bu bayraklar temizler.

## <a name="vclrfradixanchor6"></a> sayı tabanı

`dec`, `oct`, Ve `hex` manipülatörleri giriş ve çıkış için varsayılan taban ayarlayın. Örneğin, eklediğiniz `hex` çıkış akışına, nesnenin içine işleyici doğru bir şekilde onaltılık çıkış biçimi tamsayı iç veri gösterimine çevirir. Sayılar, a ile f ile basamak küçük harflerle [büyük](../standard-library/ios-functions.md#uppercase) bayrağı (varsayılan) silin; Aksi takdirde, büyük harf görüntülenir. Varsayılan sayı tabanı `dec` (ondalık).

## <a name="quoted-strings-c14"></a>Tırnak içine alınmış dizeler (C ++ 14)

Bir akışa bir dize eklediğinizde, kolayca stringstream::str() üye işlevini çağırarak aynı dize alabilir. Çıkarma işleci yeni bir dize daha sonraki bir noktada akışa eklemek için kullanmak istiyorsanız, ancak beklenmeyen bir sonuç çünkü alabilirsiniz >> işleci varsayılan olarak, ilk boşluk karakteri ile karşılaştığında durdurur.

```cpp
std::stringstream ss;
std::string inserted = "This is a sentence.";
std::string extracted;

ss << inserted;
ss >> extracted;

std::cout << inserted;     //  This is a sentence.
std::cout << extracted;    //  This
```

Bu davranış el ile üstesinden gelebilir, ancak daha kullanışlı, C ++ 14 dize gidiş dönüşü yapmak ekler `std::quoted` işleyici içinde akış \<iomanip >. Ekleme sırasında `quoted()` ayırıcı dizenin çevreleyen (çift tırnak işareti ' "' varsayılan olarak) ve son sınırlayıcı karşılaşana kadar tüm karakterleri ayıklamak için akış ayıklama sırasında yönetir. Bir kaçış karakterini kaçış karakterli tüm katıştırılmış tırnak işaretleri ('\\\\' varsayılan olarak).

Sınırlayıcılar yalnızca akış nesnesinde var; Ayıklanan dizenin olmadıkları ancak bunlar tarafından döndürülen dize mevcut [basic_stringstream::str](../standard-library/basic-stringstream-class.md#str).

Tırnak işaretli işleci Giriş dizesinin bir ham dize değişmez değeri olup veya normal bir dize bağımsız olarak yararlı olacak şekilde nasıl bir dize kodda gösterilir ekleme ve çıkarma işlemleri boşluk davranışını bağımsızdır. Giriş dizisinde ne olursa olsun, biçimi katıştırılmış teklifleri, satır sonu, sekmeleri ve bu şekilde devam eder ve tüm bu quoted() işleyici tarafından korunur.

Daha fazla bilgi ve tam kod örnekleri için bkz. [teklif](../standard-library/iomanip-functions.md#quoted).

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
