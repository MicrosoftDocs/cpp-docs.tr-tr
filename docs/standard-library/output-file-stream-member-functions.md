---
title: Çıkış Dosya Akışı Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
ms.openlocfilehash: eba627c69437754a9c0a819167443aa00c025fef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621773"
---
# <a name="output-file-stream-member-functions"></a>Çıkış Dosya Akışı Üye İşlevleri

Çıkış akışı üye işlevleri, üç tür vardır: manipülatörleri için biçimlendirilmemiş gerçekleştirmesi eşdeğer olan yazma işlemleri ve, aksi takdirde akış değiştirme durumunu ve herhangi bir eşdeğer işleyici veya ekleme işleci vardır. Sıralı, biçimlendirilmiş çıkış için yalnızca ekleme işleçlerini ve manipülatörleri kullanabilirsiniz. Rastgele erişim ikili disk çıkış için diğer üye işlevlerini içeren veya içermeyen ekleme işleçlerini kullanın.

## <a name="the-open-function-for-output-streams"></a>Çıkış akışları açık işlevi

Bir çıkış dosya akışı kullanmak için ([ofstream](../standard-library/basic-ofstream-class.md)), bu akış bir oluşturucu belirli disk dosyasında ile ilişkilendirmeniz gerekir veya `open` işlevi. Kullanırsanız `open` işlevi, bir dizi dosyası ile aynı akış nesnesi yeniden kullanabilirsiniz. Her iki durumda da aynı dosyanın açıklayan bağımsız değişkenler.

Genellikle bir çıkış akışı ile ilişkili dosyayı açtığınızda, belirttiğiniz bir `open_mode` bayrağı. Bu bayraklar listesindeki numaralandırıcıların olarak tanımlanan birleştirebilirsiniz `ios` sınıfıyla Bitsel OR ( &#124; ) işleci. Bkz: [ios_base::openmode](../standard-library/ios-base-class.md#openmode) numaralandırıcıların listesi.

Üç yaygın çıkış akışı durumlar modu seçenekleri içerir:

- Bir dosya oluşturuluyor. Dosya zaten varsa, eski sürümü silindi.

   ```cpp
   ostream ofile("FILENAME");
   // Default is ios::out

   ofstream ofile("FILENAME", ios::out);
   // Equivalent to above
   ```

- Kayıtları varolan dosyaya ekleme veya bu yoksa, oluşturma.

   ```cpp
   ofstream ofile("FILENAME", ios::app);
   ```

- İki dosya teker teker aynı akışta açılıyor.

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

## <a name="the-put"></a>Koy

**Put** işlevi, çıkış akışına bir karakter yazar. Aşağıdaki iki deyim varsayılan olarak aynıdır, ancak ikinci akışın biçim bağımsız değişken tarafından etkilenir:

```cpp
cout.put('A');

// Exactly one character written
cout <<'A'; // Format arguments 'width' and 'fill' apply
```

## <a name="the-write"></a>Yazma

`write` İşlevi bir bellek bloğu için bir çıkış dosya akışı yazar. Uzunluk değişkeni, yazılan bayt sayısını belirtir. Bu örnek, bir çıkış dosya akışı oluşturur ve ikili değeri Yazar `Date` ona yapısı:

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

`write` İşlevi değil Durdur tam sınıf yapısı yazıldığı şekilde bir null karakteri ulaştığında. İşlev iki bağımsız değişkeni alır: bir **char** işaretçi ve yazılacak karakter sayısı. Gerekli dönüştürme Not **char** <strong>\*</strong> yapısı nesnenin adresi önce.

## <a name="the-seekp-and-tellp-functions"></a>Seekp ve tellp işlevleri

Bir çıkış dosya akışı veri sonraki yazılacak olduğu konuma işaret eden bir iç işaretçi tutar. `seekp` Üye işlevi bu işaretçi ayarlar ve bu nedenle rastgele erişimli disk dosya çıktısı sağlar. `tellp` Üye işlevi, dosya konumu döndürür. Giriş akışı eşdeğerleri kullanan örnekler `seekp` ve `tellp`, bkz: [seekg ve tellg işlevleri](../standard-library/input-stream-member-functions.md).

## <a name="the-close-function-for-output-streams"></a>Çıkış akışları kapat işlevi

`close` Üye işlevi bir çıkış dosya akışı ile ilişkili disk dosyayı kapatır. Tüm disk çıkış tamamlamak için dosyanın kapatılması gerekir. Gerekirse, `ofstream` yok Edicisi, dosyayı kapatır, ancak kullanabileceğiniz `close` aynı stream nesne için başka bir dosyayı açmaya gerekiyorsa işlev.

Çıkış akış yok edici bir akışın dosya eksikse Oluşturucusu otomatik olarak kapatılır. veya `open` üye işlevi açık dosya. Bir dosya zaten açık veya kullanmak için bir dosya tanımlayıcısı kurucu geçirirseniz `attach` üye işlevi, dosyayı açıkça kapatın.

## <a name="vclrferrorprocessingfunctionsanchor10"></a> Hata işleme işlevleri

Bu üye işlevleri, bir akışa yazılırken hataları test etmek için kullanın:

|İşlev|Dönüş değeri|
|--------------|------------------|
|[hatalı](basic-ios-class.md#bad)|Döndürür **true** kurtarılamaz bir hata varsa.|
|[Başarısız](basic-ios-class.md#fail)|Döndürür **true** kurtarılamaz bir hata veya bir dönüştürme hatası gibi "beklenen" bir koşul ise veya dosya bulunamadı. İşleme genellikle çağrısı yapıldıktan sonra devam `clear` bir sıfır bağımsız değişken.|
|[iyi](basic-ios-class.md#good)|Döndürür **true** (kurtarılamaz veya diğer) hiçbir hata koşulu ve dosya sonu bayrağı ayarlı değil.|
|[eof](basic-ios-class.md#eof)|Döndürür **true** dosya sonu koşulu üzerinde.|
|[Temizle](basic-ios-class.md#clear)|İç hata durumunu ayarlar. Varsayılan bağımsız değişkenleri ile çağırdıysanız, tüm hata BITS temizler.|
|[rdstate] (temel-ios-class.md #rdstate|Geçerli hata durumuna döndürür.|

**!** aynı işlevi gerçekleştirmek için işleci aşırı `fail` işlevi. Bu nedenle ifade:

```cpp
if(!cout)...
```

eşdeğerdir:

```cpp
if(cout.fail())...
```

**Void\*()** işleci aşırı tam tersi olacak şekilde **!** işleci Bu nedenle ifade:

```cpp
if(cout)...
```

eşittir:

```cpp
if(!cout.fail())...
```

**Void\*()** işleci eşit değil `good` çünkü dosya sonunda için test yok.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
