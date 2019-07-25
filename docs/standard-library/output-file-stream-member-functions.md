---
title: Çıkış Dosya Akışı Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
ms.openlocfilehash: 8c23008d0c46a532f11e89442328ed25cc203077
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453063"
---
# <a name="output-file-stream-member-functions"></a>Çıkış Dosya Akışı Üye İşlevleri

Çıkış akışı üye işlevlerinde üç tür vardır: yapılan değişiklikler, biçimlendirilmemiş yazma işlemleri gerçekleştirenler ve başka türlü akış durumunu değiştiren ve eşdeğer bir işleme ya da ekleme işlecine sahip olanlar. Sıralı, biçimli çıkışlar için yalnızca ekleme işleçleri ve düzenlemeleri kullanabilirsiniz. Rastgele erişimli ikili disk çıktısı için, ekleme işleçleri içeren veya içermeyen diğer üye işlevlerini kullanırsınız.

## <a name="the-open-function-for-output-streams"></a>Çıkış akışları için Open Işlevi

Çıkış dosyası akışını ([ofstream](../standard-library/basic-ofstream-class.md)) kullanmak için, bu akışı oluşturucuda veya `open` işlevdeki belirli bir disk dosyasıyla ilişkilendirmeniz gerekir. `open` İşlevini kullanırsanız, aynı Stream nesnesini bir dizi dosya ile yeniden kullanabilirsiniz. Her iki durumda da, dosyayı tanımlayan bağımsız değişkenler aynıdır.

Bir çıkış akışıyla ilişkili dosyayı açtığınızda, genellikle bir `open_mode` bayrak belirtirsiniz. Bit düzeyinde OR ( `ios` &#124; ) işleci ile sınıfta Numaralandırıcılar olarak tanımlanan bu bayrakları birleştirebilirsiniz. Numaralandırıcıların listesi için bkz. [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) .

Üç ortak çıkış akışı durumunda mod seçenekleri yer alabilir:

- Dosya oluşturuluyor. Dosya zaten varsa, eski sürüm silinir.

   ```cpp
   ostream ofile("FILENAME");
   // Default is ios::out

   ofstream ofile("FILENAME", ios::out);
   // Equivalent to above
   ```

- Kayıtlar var olan bir dosyaya ekleniyor veya yoksa bir dosya oluşturuluyor.

   ```cpp
   ofstream ofile("FILENAME", ios::app);
   ```

- İki dosyayı tek seferde, aynı akışta açma.

   ```cpp
   ofstream ofile();
   ofile.open("FILE1", ios::in);
   // Do some output
   ofile.close();    // FILE1 closed
   ofile.open("FILE2", ios::in);
   // Do some more output
   ofile.close();    // FILE2 closed
   // When ofile goes out of scope it is destroyed.
   ```

## <a name="the-put"></a>Put

**PUT** işlevi, çıkış akışına bir karakter yazar. Aşağıdaki iki deyim varsayılan olarak aynıdır, ancak ikincisi akışın biçim bağımsız değişkenlerinden etkilenir:

```cpp
cout.put('A');

// Exactly one character written
cout <<'A'; // Format arguments 'width' and 'fill' apply
```

## <a name="the-write"></a>Yazma

`write` İşlevi bir bellek bloğunu çıkış dosyası akışına yazar. Length bağımsız değişkeni yazılan bayt sayısını belirtir. Bu örnek, bir çıkış dosyası akışı oluşturur ve `Date` yapının ikili değerini buna Yazar:

```cpp
// write_function.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;

struct Date
{
   int mo, da, yr;
};

int main( )
{
   Date dt = { 6, 10, 92 };
   ofstream tfile( "date.dat" , ios::binary );
   tfile.write( (char *) &dt, sizeof dt );
}
```

`write` İşlev null bir karaktere ulaştığında durdurulmaz, bu nedenle tüm sınıf yapısı yazılır. İşlev iki bağımsız değişken alır: bir **char** işaretçisi ve yazılacak karakter sayısı. Yapı nesnesinin adresinden önce **char** <strong>\*</strong> için gereken noktaya dönüştürmeyi aklınızda edin.

## <a name="the-seekp-and-tellp-functions"></a>Seekp ve tellp Işlevleri

Bir çıkış dosyası akışı, verilerin sonraki yazıldığı konuma işaret eden bir iç işaretçi tutar. `seekp` Üye işlevi bu işaretçiyi ayarlar ve bu nedenle Rastgele erişimli disk dosyası çıkışı sağlar. `tellp` Üye işlevi dosya konumunu döndürür. `seekp` Ve`tellp`için giriş akışı eşdeğerlerini kullanan örnekler için bkz. [seekg ve tellg işlevleri](../standard-library/input-stream-member-functions.md).

## <a name="the-close-function-for-output-streams"></a>Çıkış akışları için Close Işlevi

Üye `close` işlevi, bir çıkış dosyası akışıyla ilişkili disk dosyasını kapatır. Tüm disk çıkışını tamamlaması için dosyanın kapatılması gerekir. Gerekirse, `ofstream` yıkıcı dosyayı sizin için kapatır, ancak aynı Stream nesnesi için başka bir dosya `close` açmanız gerekiyorsa bu işlevi kullanabilirsiniz.

Çıkış akışı yok edicisi, yalnızca Oluşturucu veya `open` üye işlevi dosyayı açarsa bir akışın dosyasını otomatik olarak kapatır. Oluşturucuyu zaten açık olan bir dosya için bir dosya tanımlayıcısı geçirirseniz veya `attach` üye işlevini kullanırsanız, dosyayı açık olarak kapatmanız gerekir.

## <a name="vclrferrorprocessingfunctionsanchor10"></a>Işlevler Işlenirken hata oluştu

Bir akışa yazarken hataları sınamak için bu üye işlevleri kullanın:

|İşlev|Dönüş değeri|
|--------------|------------------|
|[Hatalı](basic-ios-class.md#bad)|Kurtarılamaz bir hata varsa **true** döndürür.|
|[Neden](basic-ios-class.md#fail)|Kurtarılamaz bir hata ya da bir dönüştürme hatası gibi "beklenen" koşul veya dosya bulunamazsa **true** değeri döndürür. İşleme, genellikle sıfır bağımsız değişkenle yapılan `clear` çağrıdan sonra sürdürülür.|
|[iyi](basic-ios-class.md#good)|Hata koşulu yoksa (kurtarılamaz veya tersi) ve dosya sonu bayrağı ayarlanmamışsa **true** değerini döndürür.|
|[eof](basic-ios-class.md#eof)|Dosya sonu koşulunda **true** değerini döndürür.|
|[lediğiniz](basic-ios-class.md#clear)|İç hata durumunu ayarlar. Varsayılan bağımsız değişkenlerle çağrılırsa, tüm hata bitlerini temizler.|
|rdstate (temel-iOS-Class. MD # rdstate|Geçerli hata durumunu döndürür.|

**!** işleç, `fail` işlevle aynı işlevi gerçekleştirmek için aşırı yüklendi. Bu nedenle ifadesi:

```cpp
if(!cout)...
```

eşdeğerdir:

```cpp
if(cout.fail())...
```

**Void\*()** işleci, öğesinin tersi olacak şekilde aşırı yüklenmiştir **!** işlecinde Bu nedenle ifadesi:

```cpp
if(cout)...
```

Şuna eşittir:

```cpp
if(!cout.fail())...
```

**Void\*()** işleci, dosyanın sonuna yönelik test `good` olmadığı için buna eşdeğer değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)
