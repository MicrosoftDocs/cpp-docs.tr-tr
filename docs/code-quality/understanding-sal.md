---
title: SAL'ı Anlama
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a94d6907-55f2-4874-9571-51d52d6edcfd
ms.openlocfilehash: 7f8eeaad94efd77b5f63b9af524efa76ac00cae7
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418734"
---
# <a name="understanding-sal"></a>SAL'ı Anlama

Microsoft kaynak kodu ek açıklama dili (SAL), bir işlevin parametrelerini nasıl kullandığını, kendileri hakkında yaptığı varsayımları ve tamamlandığında yaptığı garanti sayısını betimleyen bir dizi ek açıklama sağlar. Ek açıklamalar `<sal.h>`üstbilgi dosyasında tanımlanmıştır. İçin C++ Visual Studio kod analizi, işlevlerinin analizini DEğIşTIRMEk için sal ek açıklamalarını kullanır. Windows sürücü geliştirme için SAL 2,0 hakkında daha fazla bilgi için bkz. [Windows sürücüleri Için sal 2,0 ek açıklamaları](/windows-hardware/drivers/devtest/sal-2-annotations-for-windows-drivers).

Yerel olarak, C C++ ve geliştiricilerin sürekli olarak hızlı bir şekilde ifade ve ınvaryans sağlaması için yalnızca sınırlı yollar sağlar. SAL ek açıklamalarını kullanarak, bunları kullanan geliştiricilerin bunları nasıl kullanacağınızı daha iyi anlayabilmesi için işlevlerinizi daha ayrıntılı bir şekilde tanımlayabilirsiniz.

## <a name="what-is-sal-and-why-should-you-use-it"></a>SAL nedir ve neden kullanmalıyım?

Yalnızca belirtilen SAL, derleyicinin kodunuzu sizin yerinize denetlemesini sağlamak için pahalı bir yoldur.

### <a name="sal-makes-code-more-valuable"></a>SAL, kodu daha değerli hale getirir

SAL, kod tasarımınızı hem insanlar hem de kod analizi araçları için daha anlaşılır hale getirmenize yardımcı olabilir. `memcpy`C çalışma zamanı işlevini gösteren bu örneği göz önünde bulundurun:

```cpp

void * memcpy(
   void *dest,
   const void *src,
   size_t count
);
```

Bu işlevin ne yaptığını söyleyebilir misiniz? Bir işlev uygulandığında veya çağrıldığında, programın doğruluğunu sağlamak için bazı özellikler tutulması gerekir. Yalnızca örnekteki gibi bir bildirime bakarak ne olduğunu bilemezsiniz. SAL ek açıklamaları olmadan belgeleri veya kod açıklamalarını bilmeniz gerekir. İşte `memcpy` MSDN belgeleri şöyle diyor:

> "Src 'nin Count baytlarını hedefe kopyalar. Kaynak ve hedef çakışırsa, memcservicebehavior davranışı tanımsızdır. Çakışan bölgeleri işlemek için memmove kullanın.
> **Güvenlik notno:** Hedef arabelleğinin boyut veya Kaynak arabelleğinden daha büyük olduğundan emin olun. Daha fazla bilgi için bkz. arabellek taşmalarını önleme. "

Belgeler, kodunuzun, programın doğruluğunu sağlamak için belirli özellikleri sürdürmek için sahip olduğunu öneren birkaç bilgi içerir:

- `memcpy`, bayt `count` Kaynak arabelleğinden hedef arabelleğe kopyalar.

- Hedef arabellek en az kaynak arabelleği kadar büyük olmalıdır.

Ancak, derleyici belgeleri veya resmi olmayan açıklamaları okuyamaz. İki arabellek ve `count`arasında bir ilişki olduğunu ve aynı zamanda bir ilişki hakkında etkili bir şekilde tahmin edemediğini bilmez. SAL, burada gösterildiği gibi işlevin özellikleri ve uygulanması hakkında daha fazla açıklık sağlayabilir:

```cpp

void * memcpy(
   _Out_writes_bytes_all_(count) void *dest,
   _In_reads_bytes_(count) const void *src,
   size_t count
);
```

Bu ek açıklamaların MSDN belgelerindeki bilgilere benzediğine dikkat edin, ancak bunlar daha kısa ve anlamlı bir düzene uyar. Bu kodu okurken, bu işlevin özelliklerini hızlı bir şekilde anlayabilmeniz ve arabellek taşması güvenlik sorunlarından kaçının. Daha da iyisi, SAL 'un sağladığı anlam desenleri, olası hataların erken keşfinde otomatik kod çözümleme araçlarının verimliliğini ve verimliliğini artırır. Birisinin bu `wmemcpy`önemlidir uygulamasını yazabileceğini düşünün:

```cpp

wchar_t * wmemcpy(
   _Out_writes_all_(count) wchar_t *dest,
   _In_reads_(count) const wchar_t *src,
   size_t count)
{
   size_t i;
   for (i = 0; i <= count; i++) { // BUG: off-by-one error
      dest[i] = src[i];
   }
   return dest;
}
```

Bu uygulama, bir ortak-tek hatası içerir. Neyse ki, kod yazarı SAL arabellek boyutu ek açıklamasını içeriyordu — bir kod Analizi Aracı bu işlevi tek başına çözümleyerek hatayı yakalayabilir.

### <a name="sal-basics"></a>SAL temel kavramları

SAL, kullanım düzenine göre sınıflandırılan dört temel parametre türünü tanımlar.

|Kategori|Parametre ek açıklaması|Açıklama|
|--------------|--------------------------|-----------------|
|**Çağrılan işleve giriş**|`_In_`|Veriler çağrılan işleve geçirilir ve salt okunurdur.|
|**Çağrılan işleve giriş ve arayana çıkış**|`_Inout_`|Kullanılabilir veriler işleve geçirilir ve potansiyel olarak değiştirilebilir.|
|**Çağırana çıkış**|`_Out_`|Çağıran, yazmak için çağrılan işlev için alan sağlar. Çağrılan işlev verileri bu alana yazar.|
|**Arayan işaretçisinin çıkışı**|`_Outptr_`|**Arayana çıkış**gibi. Çağrılan işlev tarafından döndürülen değer bir işaretçidir.|

Bu dört temel ek açıklama, çeşitli yollarla daha açık hale getirilebilir. Varsayılan olarak, açıklamalı işaretçi parametrelerinin gerekli olduğu varsayılır — işlevin başarılı olması için NULL olmayan bir değer olmalıdır. Temel ek açıklamaların en yaygın olarak kullanılan çeşitlemesi, bir işaretçi parametresinin isteğe bağlı olduğunu belirtir; NULL ise, işlev işini gerçekleştirirken yine de başarılı olabilir.

Bu tabloda, gerekli ve isteğe bağlı parametrelerin nasıl ayırt edilebilmesi gösterilmektedir:

||Parametreler gereklidir|Parametreler isteğe bağlıdır|
|-|-----------------------------|-----------------------------|
|**Çağrılan işleve giriş**|`_In_`|`_In_opt_`|
|**Çağrılan işleve giriş ve arayana çıkış**|`_Inout_`|`_Inout_opt_`|
|**Çağırana çıkış**|`_Out_`|`_Out_opt_`|
|**Arayan işaretçisinin çıkışı**|`_Outptr_`|`_Outptr_opt_`|

Bu ek açıklamalar, olası başlatılmamış değerleri belirlemenize yardımcı olur ve geçersiz null işaretçisi biçimsel ve doğru bir şekilde kullanır. NULL değerini gerekli bir parametreye geçirmek kilitlenmeye neden olabilir veya bir "başarısız" hata kodunun döndürülmesine neden olabilir. Her iki durumda da işlev işini yaparken başarılı olamaz.

## <a name="sal-examples"></a>SAL örnekleri

Bu bölümde, temel SAL ek açıklamaları için kod örnekleri gösterilmektedir.

### <a name="using-the-visual-studio-code-analysis-tool-to-find-defects"></a>Kusurları bulmak için Visual Studio Code Analysis aracını kullanma

Örneklerde, kod kusurlarını bulmak için Visual Studio Code Analiz Aracı SAL ek açıklamalarıyla birlikte kullanılır. Bunun nasıl yapılacağını aşağıda bulabilirsiniz.

#### <a name="to-use-visual-studio-code-analysis-tools-and-sal"></a>Visual Studio Code Analysis araçları ve SAL 'ı kullanmak için

1. Visual Studio 'da SAL ek açıklamalarını C++ içeren bir proje açın.

1. Menü çubuğunda **Oluştur**, **çözüm üzerinde Kod analizini Çalıştır**' ı seçin.

     Bu bölümde\_ örnekte \_göz önünde bulundurun. Kod analizini üzerinde çalıştırırsanız, bu uyarı görüntülenir:

    > **C6387 geçersiz parametre değeri** ' pInt ', ' 0 ' olabilir: Bu, ' InCallee ' işlevinin belirtimine bağlı kalmıyor.

### <a name="example-the-_in_-annotation"></a>Örnek:\_ ek açıklamasında \_

`_In_` ek açıklaması şunları gösterir:

- Parametrenin geçerli olması ve değiştirilmeyecek olması gerekir.

- İşlev yalnızca tek öğeli arabellekten okunacak.

- Çağıranın arabelleği sağlaması ve başlatması gerekir.

- `_In_` "salt okunurdur" belirtir. Yaygın bir hata, bunun yerine `_Inout_` ek açıklamasına sahip olması gereken bir parametreye `_In_` uygulanmamalıdır.

- `_In_` izin verilir, ancak işaretçi olmayan bir şekilde çözümleyici tarafından yok sayılır.

```cpp
void InCallee(_In_ int *pInt)
{
   int i = *pInt;
}

void GoodInCaller()
{
   int *pInt = new int;
   *pInt = 5;

   InCallee(pInt);
   delete pInt;
}

void BadInCaller()
{
   int *pInt = NULL;
   InCallee(pInt); // pInt should not be NULL
}
```

Bu örnekte Visual Studio Code analizini kullanıyorsanız, çağıranların `pInt`için başlatılmış bir arabelleğe null olmayan bir işaretçi geçirdiğinden emin olur. Bu durumda `pInt` işaretçi NULL olamaz.

### <a name="example-the-_in_opt_-annotation"></a>Örnek: \_\_opt\_ ek açıklaması

`_In_opt_`, giriş parametresinin NULL olmasına izin verildiğinden ve bu nedenle işlevin bunu denetlemesi gerektiği durumlar dışında `_In_`.

```cpp

void GoodInOptCallee(_In_opt_ int *pInt)
{
   if(pInt != NULL) {
      int i = *pInt;
   }
}

void BadInOptCallee(_In_opt_ int *pInt)
{
   int i = *pInt; // Dereferencing NULL pointer 'pInt'
}

void InOptCaller()
{
   int *pInt = NULL;
   GoodInOptCallee(pInt);
   BadInOptCallee(pInt);
}
```

Visual Studio Code analizi, işlevin arabelleğe erişmeden önce NULL olduğunu kontrol ettiğini doğrular.

### <a name="example-the-_out_-annotation"></a>Örnek: \_Out\_ ek açıklaması

`_Out_`, öğe arabelleğini işaret eden NULL olmayan bir işaretçinin geçirildiği ve işlevin öğeyi Başlatan ortak bir senaryoyu destekler. Çağıranın çağrıdan önce arabelleği başlatması gerekmez; çağrılan işlev, döndürülmadan önce başlatmayı taahhüt eder.

```cpp
void GoodOutCallee(_Out_ int *pInt)
{
   *pInt = 5;
}

void BadOutCallee(_Out_ int *pInt)
{
   // Did not initialize pInt buffer before returning!
}

void OutCaller()
{
   int *pInt = new int;
   GoodOutCallee(pInt);
   BadOutCallee(pInt);
   delete pInt;
}
```

Visual Studio Code çözümleme aracı, çağıranın NULL olmayan bir işaretçiyi `pInt` arabelleğine geçirdiğinden ve arabelleğin döndürülmeden önce işlevin tarafından başlatıldığını doğrular.

### <a name="example-the-_out_opt_-annotation"></a>Örnek: \_Out\_opt\_ ek açıklaması

`_Out_opt_`, parametresinin NULL olmasına izin verildiğinden ve bu nedenle işlevin bunu denetlemesi gerektiği durumlar dışında `_Out_`.

```cpp
void GoodOutOptCallee(_Out_opt_ int *pInt)
{
   if (pInt != NULL) {
      *pInt = 5;
   }
}

void BadOutOptCallee(_Out_opt_ int *pInt)
{
   *pInt = 5; // Dereferencing NULL pointer 'pInt'
}

void OutOptCaller()
{
   int *pInt = NULL;
   GoodOutOptCallee(pInt);
   BadOutOptCallee(pInt);
}
```

Visual Studio Code analizi, bu işlevin, `pInt` başvurulmadan önce NULL olduğunu kontrol ettiğini ve `pInt` NULL olmaması durumunda, arabelleğin döndürülmeden önce işlev tarafından başlatıldığını doğrular.

### <a name="example-the-_inout_-annotation"></a>Örnek: \_Iç\_ ek açıklaması

`_Inout_`, işlevi tarafından değiştirilebilen bir işaretçi parametresine açıklama eklemek için kullanılır. İşaretçi, çağrıdan önce geçerli başlatılmış verileri göstermelidir ve değişse bile, yine de dönüş üzerinde geçerli bir değere sahip olmalıdır. Ek açıklama, işlevin tek öğeli arabelleğe serbestçe okunabilir ve yazılabilir olabileceğini belirtir. Çağıranın arabelleği sağlaması ve başlatması gerekir.

> [!NOTE]
> `_Out_`gibi, `_Inout_` değiştirilebilir bir değer için de geçerlidir.

```cpp
void InOutCallee(_Inout_ int *pInt)
{
   int i = *pInt;
   *pInt = 6;
}

void InOutCaller()
{
   int *pInt = new int;
   *pInt = 5;
   InOutCallee(pInt);
   delete pInt;
}

void BadInOutCaller()
{
   int *pInt = NULL;
   InOutCallee(pInt); // 'pInt' should not be NULL
}
```

Visual Studio Code analizi, çağıranların `pInt`için başlatılmış bir arabelleğe NULL olmayan bir işaretçi geçirmektedir ve döndürülmeden önce `pInt` hala NULL değil ve arabelleğin başlatıldığını doğrular.

### <a name="example-the-_inout_opt_-annotation"></a>Örnek: \_InOut\_opt\_ ek açıklaması

`_Inout_opt_`, giriş parametresinin NULL olmasına izin verildiğinden ve bu nedenle işlevin bunu denetlemesi gerektiği durumlar dışında `_Inout_`.

```cpp
void GoodInOutOptCallee(_Inout_opt_ int *pInt)
{
   if(pInt != NULL) {
      int i = *pInt;
      *pInt = 6;
   }
}

void BadInOutOptCallee(_Inout_opt_ int *pInt)
{
   int i = *pInt; // Dereferencing NULL pointer 'pInt'
   *pInt = 6;
}

void InOutOptCaller()
{
   int *pInt = NULL;
   GoodInOutOptCallee(pInt);
   BadInOutOptCallee(pInt);
}
```

Visual Studio Code analizi, bu işlevin arabelleğe erişmeden önce NULL olduğunu denetlediğini ve `pInt` NULL olmaması durumunda arabelleğin döndürülmeden önce işlev tarafından başlatıldığını doğrular.

### <a name="example-the-_outptr_-annotation"></a>Örnek: \_Outptr\_ ek açıklaması

`_Outptr_`, bir işaretçiye dönmesi amaçlanan bir parametreye açıklama eklemek için kullanılır.  Parametrenin kendisi NULL olmamalı ve çağrılan işlev içinde NULL olmayan bir işaretçi döndürüyor ve işaretçi başlatılmış verileri işaret ediyor.

```cpp
void GoodOutPtrCallee(_Outptr_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 5;

   *pInt = pInt2;
}

void BadOutPtrCallee(_Outptr_ int **pInt)
{
   int *pInt2 = new int;
   // Did not initialize pInt buffer before returning!
   *pInt = pInt2;
}

void OutPtrCaller()
{
   int *pInt = NULL;
   GoodOutPtrCallee(&pInt);
   BadOutPtrCallee(&pInt);
}
```

Visual Studio Code analizi, çağıranın `*pInt`için NULL olmayan bir işaretçi geçirdiğinden ve arabelleğin döndürülmeden önce işlev tarafından başlatıldığını doğrular.

### <a name="example-the-_outptr_opt_-annotation"></a>Örnek: \_Outptr\_opt\_ ek açıklaması

`_Outptr_opt_` `_Outptr_`, parametrenin isteğe bağlı olması dışında, çağıran, parametre için NULL bir işaretçiye geçebilirler.

```cpp
void GoodOutPtrOptCallee(_Outptr_opt_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 6;

   if(pInt != NULL) {
      *pInt = pInt2;
   }
}

void BadOutPtrOptCallee(_Outptr_opt_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 6;
   *pInt = pInt2; // Dereferencing NULL pointer 'pInt'
}

void OutPtrOptCaller()
{
   int **ppInt = NULL;
   GoodOutPtrOptCallee(ppInt);
   BadOutPtrOptCallee(ppInt);
}
```

Visual Studio Code analizi, bu işlevin, `*pInt` başvurulmadan önce NULL olduğunu kontrol ettiğini ve arabelleğin döndürülmeden önce işlev tarafından başlatıldığını doğrular.

### <a name="example-the-_success_-annotation-in-combination-with-_out_"></a>Örnek: \_out ile birlikte \_başarılı\_ ek açıklaması\_

Ek açıklamalar, çoğu nesneye uygulanabilir.  Özellikle, bir işlevin tamamına açıklama ekleyebilirsiniz.  Bir işlevin en belirgin özelliklerinden biri, başarılı veya başarısız olmasına neden olabilir. Ancak, bir arabellek ve boyutu arasındaki ilişki gibi, C/C++ işlev başarısı veya başarısızlığı ifade edemez. `_Success_` ek açıklamasını kullanarak bir işlevin başarısını nasıl göründüğünü söyleyebilirsiniz.  `_Success_` ek açıklamasına yönelik parametre, true olduğunda işlevin başarılı olduğunu gösterir. İfade, ek açıklama ayrıştırıcısının işleyebileceği herhangi bir şey olabilir. İşlev döndürmede sonra ek açıklamaların etkileri yalnızca işlev başarılı olduğunda geçerlidir. Bu örnek, doğru şeyi yapmak için `_Success_` `_Out_` nasıl etkileşime gireceğini gösterir. Dönüş değerini göstermek için `return` anahtar sözcüğünü kullanabilirsiniz.

```cpp
_Success_(return != false) // Can also be stated as _Success_(return)
bool GetValue(_Out_ int *pInt, bool flag)
{
   if(flag) {
      *pInt = 5;
      return true;
   } else {
      return false;
   }
}
```

`_Out_` ek açıklaması, arayanın `pInt`için bir arabelleğe NULL olmayan bir işaretçi geçirdiğini ve arabelleğin döndürülmeden önce işlevin tarafından başlatıldığını doğrulamasına Visual Studio Code olanak sağlar.

## <a name="sal-best-practice"></a>SAL En Iyi uygulama

### <a name="adding-annotations-to-existing-code"></a>Varolan koda ek açıklamalar ekleme

SAL, kodunuzun güvenliğini ve güvenilirliğini artırmanıza yardımcı olabilecek güçlü bir teknolojidir. SAL 'yı öğrendikten sonra, günlük çalışmanıza yeni beceriye uygulayabilirsiniz. Yeni kodda, içinde tasarım yaparak SAL tabanlı belirtimleri kullanabilirsiniz; Eski kodda, ek açıklamaları artımlı olarak ekleyebilir ve böylece her güncelleştirdiğinizde avantajların artırılmasını sağlayabilirsiniz.

Microsoft genel üstbilgileri zaten açıklama eklenmiş. Bu nedenle, projelerinizden önce en avantajdan yararlanmak için Win32 API 'Leri çağıran yaprak düğüm işlevleri ve işlevleri Not almanızı öneririz.

### <a name="when-do-i-annotate"></a>Ne zaman not ekleyebilirim?

Bazı yönergeler aşağıda verilmiştir:

- Tüm işaretçi parametrelerine Not ekle.

- Kod analizinin arabellek ve işaretçi güvenliğini sağlamak için değer aralığı açıklamalarını not edin.

- Kilitleme kuralları ekleme ve yan etkileri kilitleme. Daha fazla bilgi için bkz. [kilitleme davranışına açıklama ekleme](../code-quality/annotating-locking-behavior.md).

- Sürücü özelliklerine ve etki alanına özgü özelliklere açıklama ekleyin.

Ya da tüm parametrelere ek açıklama ekleyebilirsiniz ve bu da ek açıklamaların gerçekleştirilip yapılmayı kolayca kontrol edebilirsiniz.

## <a name="related-resources"></a>İlgili Kaynaklar

[Kod Analizi ekip blogu](https://blogs.msdn.microsoft.com/codeanalysis/)

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [İşlev Parametrelerini ve Dönüş Değerlerini Açıklama](../code-quality/annotating-function-parameters-and-return-values.md)
- [İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)
- [Yapıları ve Sınıfları Yorumlama](../code-quality/annotating-structs-and-classes.md)
- [Kilitlenme Davranışını Yorumlama](../code-quality/annotating-locking-behavior.md)
- [Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [En İyi Yöntemler ve Örnekler](../code-quality/best-practices-and-examples-sal.md)
