---
title: İşlev Parametrelerini ve Dönüş Değerlerini Açıklama
ms.date: 10/15/2019
ms.topic: conceptual
f1_keywords:
- _Outptr_opt_result_bytebuffer_to_
- _Inout_updates_all_opt_
- _Post_equal_to_
- _Outptr_opt_result_maybenull_
- _Out_writes_bytes_all_
- _Out_writes_all_opt_
- _In_opt_
- _Outptr_
- _Outptr_result_maybenull_
- _Outref_result_bytebuffer_all_maybenull_
- _Inout_updates_opt_z_
- _Inout_updates_z_
- _Out_writes_
- _Out_writes_to_ptr_opt_z_
- _In_reads_to_ptr_opt_
- _Ret_writes_to_maybenull_
- _Outref_result_maybenull_
- _Ret_writes_bytes_
- _Outptr_result_bytebuffer_
- _Out_writes_opt_
- _Inout_updates_bytes_opt_
- _In_z_
- _Inout_updates_to_
- _Ret_maybenull_
- _Ret_writes_bytes_to_
- _Ret_z_
- _COM_Outptr_
- _Ret_maybenull_z_
- _Out_opt_
- _In_reads_opt_z_
- _Outptr_result_bytebuffer_to_
- _Ret_notnull_
- _COM_Outptr_opt_result_maybenull_
- _Inout_updates_to_opt_
- _Inout_updates_
- _Outptr_opt_result_buffer_
- _Outptr_result_buffer_to_
- _Out_writes_to_ptr_opt_
- _Out_writes_bytes_all_opt_
- _Inout_updates_all_
- _Deref_inout_range_
- _Ret_writes_
- _Out_writes_z_
- _Ret_writes_to_
- _Out_writes_to_ptr_z_
- _Out_writes_bytes_to_opt_
- _In_reads_or_z_
- _Inout_updates_bytes_to_
- _In_reads_z_
- _In_opt_z_
- _Outref_result_buffer_maybenull_
- _Ret_range_
- _COM_Outptr_opt_
- _Ouptr_opt_result_maybenull_z_
- _In_reads_opt_
- _Inout_
- _Field_range_
- _Ret_writes_z_
- _Out_writes_to_
- _Out_writes_to_ptr_
- _Inout_opt_z_
- _Outref_
- _Deref_out_range_
- _Outref_result_buffer_
- _Outref_result_buffer_to_
- _Outref_result_bytebuffer_to_maybenull_
- _In_reads_bytes_
- _Outptr_opt_result_buffer_to_
- _Outref_result_buffer_all_
- _Out_writes_bytes_to_
- _Result_zeroonfailure_
- _In_reads_bytes_opt_
- _Outref_result_buffer_to_maybenull_
- _Outref_result_bytebuffer_all_
- _Outref_result_buffer_all_maybenull_
- _Ret_writes_maybenull_z_
- _In_range_
- _Inout_updates_bytes_all_opt_
- _Outref_result_bytebuffer_to_
- _Inout_updates_bytes_to_opt_
- _Pre_equal_to_
- _Ret_writes_bytes_maybenull_
- _COM_Outptr_result_maybenull_
- _Ret_writes_maybenull_
- _Out_writes_bytes_
- _Outptr_opt_
- _Out_writes_opt_z_
- _Outref_result_nullonfailure_
- _Outptr_opt_result_z_
- _Inout_opt_
- _Deref_in_range_
- _Outptr_result_z_
- _In_reads_to_ptr_opt_z_
- _Struct_size_bytes_
- _Outptr_result_nullonfailure_
- _In_
- _Inout_updates_bytes_
- _In_reads_to_ptr_z_
- _Ret_writes_bytes_to_maybenull
- _Outptr_opt_result_nullonfailure_
- _In_reads_to_ptr_
- _Outptr_result_buffer_
- _Out_
- _Outref_result_bytebuffer_maybenull_
- _Outptr_result_maybenull_z_
- _In_reads_
- _Inout_updates_opt_
- _Out_writes_to_opt_
- _Outptr_opt_result_bytebuffer_
- _Out_writes_all_
- _Out_range_
- _Inout_updates_bytes_all_
- _Inout_z_
- _Outref_result_bytebuffer_
- _Result_nullonfailure_
- _Ret_null_
- _Scanf_format_string_
- _Scanf_s_format_string_
- _Printf_format_string_
ms.assetid: 82826a3d-0c81-421c-8ffe-4072555dca3a
ms.openlocfilehash: 21fb06d4129c4b38257b13519855f1f9dec1eaee
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77417495"
---
# <a name="annotating-function-parameters-and-return-values"></a>İşlev Parametrelerini ve Dönüş Değerlerini Açıklama

Bu makalede basit işlev parametreleri için ek açıklamaların tipik kullanımları ve yapı ve sınıf işaretçileri ve birçok arabellek türü açıklanmaktadır.  Bu makalede ayrıca ek açıklamalar için ortak kullanım desenleri gösterilmektedir. İşlevlerle ilgili ek ek açıklamalar için bkz. [Işlev davranışına açıklama ekleme](../code-quality/annotating-function-behavior.md).

## <a name="pointer-parameters"></a>İşaretçi parametreleri

Aşağıdaki tablodaki ek açıklamalar için, işaretçi parametresine açıklama eklendiğinde, işaretçi null ise çözümleyici bir hata bildirir.  Bu, işaretçiler için ve işaret edilen tüm veri öğeleri için geçerlidir.

### <a name="annotations-and-descriptions"></a>Ek açıklamalar ve açıklamalar

- `_In_`

     Yapılar, yapılar, yapılara yönelik işaretçiler ve benzeri bir giriş parametresi olan annotates.  Açıkça basit dolandırıcıklar üzerinde kullanılabilir.  Parametrenin ön durumunda geçerli olması ve değiştirilmeyecektir.

- `_Out_`

     Yapıları, yapıları, yapılara yönelik işaretçileri ve benzeri bir çıkış parametresi olan annotates.  Bunu değer döndürmeyen bir nesneye uygulamayın — Örneğin, değere göre geçirilmiş bir skaler.  Parametrenin ön durumunda geçerli olması gerekmez, ancak durum sonrası için geçerli olmalıdır.

- `_Inout_`

     İşlev tarafından değiştirilecek bir parametreyi annotates.  Hem ön durum hem de durum durumunda geçerli olmalıdır, ancak çağrıdan önce ve sonra farklı değerlere sahip olduğu varsayılır. Değiştirilebilir bir değere uygulamanız gerekir.

- `_In_z_`

     Giriş olarak kullanılan null ile sonlandırılmış bir dize işaretçisi.  Dize, ön durumunda geçerli olmalıdır.  Doğru ek açıklamaların zaten bulunduğu `PSTR`türevleri tercih edilir.

- `_Inout_z_`

     Değiştirilecek, null ile sonlandırılmış bir karakter dizisine yönelik bir işaretçi.  Çağrıdan önce ve sonra geçerli olmalıdır, ancak değer değişmiş olarak kabul edilir.  Null Sonlandırıcı taşınabilir, ancak yalnızca orijinal null sonlandırıcısına kadar olan öğelere erişilebilir.

- `_In_reads_(s)`

     `_In_reads_bytes_(s)`

     İşlev tarafından okunan dizi için bir işaretçi.  Dizi, hepsi geçerli olması gereken `s` öğe boyutudur.

     `_bytes_` Variant, boyutu öğeler yerine bayt olarak verir. Bunu yalnızca boyut öğe olarak ifade edilemez ' i kullanın.  Örneğin, `char` dizeler yalnızca `wchar_t` kullanan benzer bir işlev `_bytes_` değişken kullanır.

- `_In_reads_z_(s)`

     Null sonlandırılmış ve bilinen bir boyuta sahip dizi için bir işaretçi. Null sonlandırıcısına sahip öğeler — veya null Sonlandırıcı yoksa `s`, ön durumda geçerli olmalıdır.  Boyut bayt olarak tanındığı takdirde, `s` öğe boyutuna göre ölçeklendirin.

- `_In_reads_or_z_(s)`

     Null sonlandırılmış veya bilinen bir boyut veya her ikisi içeren bir dizi işaretçisi. Null sonlandırıcısına sahip öğeler — veya null Sonlandırıcı yoksa `s`, ön durumda geçerli olmalıdır.  Boyut bayt olarak tanındığı takdirde, `s` öğe boyutuna göre ölçeklendirin.  (`strn` ailesi için kullanılır.)

- `_Out_writes_(s)`

     `_Out_writes_bytes_(s)`

     İşlev tarafından yazılacak `s` öğeleri (yanıt. bayt) dizisine yönelik bir işaretçi.  Dizi öğelerinin ön durumunda geçerli olması gerekmez ve durum sonrası için geçerli olan öğe sayısı belirtilmemiş olur.  Parametre türünde ek açıklamalar varsa, bunlar durum sonrası ' a uygulanır. Örneğin, aşağıdaki kodu göz önünde bulundurun.

     ```cpp
     typedef _Null_terminated_ wchar_t *PWSTR;
     void MyStringCopy(_Out_writes_(size) PWSTR p1, _In_ size_t size, _In_ PWSTR p2);
     ```

     Bu örnekte, çağıran, `p1`için `size` öğelerinin bir arabelleğini sağlar.  `MyStringCopy`, bu öğelerin bazılarını geçerli hale getirir. Daha da önemlisi, `PWSTR` `_Null_terminated_` ek açıklaması, `p1` durum sonrası null olarak sonlandırıldığı anlamına gelir.  Bu şekilde, geçerli öğe sayısı hala iyi tanımlanmış, ancak belirli bir öğe sayısı gerekli değildir.

     `_bytes_` Variant, boyutu öğeler yerine bayt olarak verir. Bunu yalnızca boyut öğe olarak ifade edilemez ' i kullanın.  Örneğin, `char` dizeler yalnızca `wchar_t` kullanan benzer bir işlev `_bytes_` değişken kullanır.

- `_Out_writes_z_(s)`

     `s` öğelerinin dizisine yönelik bir işaretçi.  Öğelerin ön durumunda geçerli olması gerekmez.  Durum sonrası 'de, mevcut olması gereken null Sonlandırıcı aracılığıyla bulunan öğeler geçerli olmalıdır.  Boyut bayt olarak tanındığı takdirde, `s` öğe boyutuna göre ölçeklendirin.

- `_Inout_updates_(s)`

     `_Inout_updates_bytes_(s)`

     Bir dizi için, hem okunan hem de işlevine yazılan bir işaretçi.  Bu boyut `s` öğeleridir ve ön durum ve son durum ' da geçerlidir.

     `_bytes_` Variant, boyutu öğeler yerine bayt olarak verir. Bunu yalnızca boyut öğe olarak ifade edilemez ' i kullanın.  Örneğin, `char` dizeler yalnızca `wchar_t` kullanan benzer bir işlev `_bytes_` değişken kullanır.

- `_Inout_updates_z_(s)`

     Null sonlandırılmış ve bilinen bir boyuta sahip dizi için bir işaretçi. Mevcut olması gereken null Sonlandırıcı aracılığıyla bulunan öğeler, hem ön durum hem de durum sonrası için geçerli olmalıdır.  Durum sonrası değeri, ön durumundaki değerden farklı olacak şekilde belirlenir; Bu, null Sonlandırıcı konumunu içerir. Boyut bayt olarak tanındığı takdirde, `s` öğe boyutuna göre ölçeklendirin.

- `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     `s` öğelerinin dizisine yönelik bir işaretçi.  Öğelerin ön durumunda geçerli olması gerekmez.  Durum sonrası, `c`-TH öğesine kadar olan öğeler geçerli olmalıdır.  Boyut, öğe sayısı yerine bayt olarak biliniyorsa `_bytes_` değişken kullanılabilir.

     Örnek:

     ```cpp
     void *memcpy(_Out_writes_bytes_all_(s) char *p1, _In_reads_bytes_(s) char *p2, _In_ int s);
     void *wordcpy(_Out_writes_all_(s) DWORD *p1, _In_reads_(s) DWORD *p2, _In_ int s);
     ```

- `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     İşlev tarafından hem okunan hem yazılan dizi için bir işaretçi.  Bu, tümünün ön durumunda geçerli olması gereken `s` ve `c` öğelerinin durum sonrası geçerli olması gereken bir boyut.

     `_bytes_` Variant, boyutu öğeler yerine bayt olarak verir. Bunu yalnızca boyut öğe olarak ifade edilemez ' i kullanın.  Örneğin, `char` dizeler yalnızca `wchar_t` kullanan benzer bir işlev `_bytes_` değişken kullanır.

- `_Inout_updates_all_(s)`

     `_Inout_updates_bytes_all_(s)`

     Boyut `s` öğelerinin işlevi tarafından hem okunan hem de yazılan dizi için bir işaretçi. Eşdeğer olarak tanımlanan:

     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`

     Diğer bir deyişle, ön durumunda `s` için arabellekte bulunan her öğe, ön durum ve sonrası durumunda geçerlidir.

     `_bytes_` Variant, boyutu öğeler yerine bayt olarak verir. Bunu yalnızca boyut öğe olarak ifade edilemez ' i kullanın.  Örneğin, `char` dizeler yalnızca `wchar_t` kullanan benzer bir işlev `_bytes_` değişken kullanır.

- `_In_reads_to_ptr_(p)`

     `p - _Curr_` (yani `p` eksi `_Curr_`) geçerli bir ifade olan dizinin bir işaretçisi.  `p` öncesindeki öğelerin ön durumunda geçerli olması gerekir.

    Örnek:

    ```cpp
    int ReadAllElements(_In_reads_to_ptr_(EndOfArray) const int *Array, const int *EndOfArray);
    ```

- `_In_reads_to_ptr_z_(p)`

     İfade `p - _Curr_` (yani `p` eksi `_Curr_`) geçerli bir ifade olan, null ile sonlandırılmış dizi işaretçisi.  `p` öncesindeki öğelerin ön durumunda geçerli olması gerekir.

- `_Out_writes_to_ptr_(p)`

     `p - _Curr_` (yani `p` eksi `_Curr_`) geçerli bir ifade olan dizinin bir işaretçisi.  `p` öncesindeki öğelerin ön durumunda geçerli olması gerekmez ve durum sonrası için geçerli olmalıdır.

- `_Out_writes_to_ptr_z_(p)`

     `p - _Curr_` (yani `p` eksi `_Curr_`) geçerli bir ifade olan, null ile sonlandırılmış dizi için bir işaretçi.  `p` öncesindeki öğelerin ön durumunda geçerli olması gerekmez ve durum sonrası için geçerli olmalıdır.

## <a name="optional-pointer-parameters"></a>İsteğe bağlı Işaretçi parametreleri

Bir işaretçi parametresi ek açıklaması `_opt_`içerdiğinde, parametrenin null olabileceğini gösterir. Aksi takdirde, ek açıklama `_opt_`içermeyen sürümle aynı şekilde çalışır. İşaretçi parametresi ek açıklamaların `_opt_` varyantlarıyla bir listesi aşağıda verilmiştir:

||||
|-|-|-|
|`_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`|`_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`|`_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`|

## <a name="output-pointer-parameters"></a>Çıkış Işaretçisi parametreleri

Çıkış işaretçisi parametreleri, parametre ve işaret konumu üzerinde null olma durumunu belirsizliğini ortadan kaldırmak için özel bir gösterim gerektirir.

### <a name="annotations-and-descriptions"></a>Ek açıklamalar ve açıklamalar

- `_Outptr_`

   Parametre null olamaz ve durum son durumunda, işaret edilen konum null olamaz ve geçerli olmalıdır.

- `_Outptr_opt_`

   Parametre null olabilir, ancak durum sonrası, noktadan sonra gelen konum null olamaz ve geçerli olmalıdır.

- `_Outptr_result_maybenull_`

   Parametre null olamaz ve durum son durumunda, işaret edilen konum null olabilir.

- `_Outptr_opt_result_maybenull_`

   Parametre null olabilir ve durum son durumunda, işaret edilen konum null olabilir.

  Aşağıdaki tabloda ek alt dizeler, ek açıklamanın anlamını daha fazla nitelemek için ek bir açıklama adına eklenir.  Çeşitli alt dizeler `_z`, `_COM_`, `_buffer_`, `_bytebuffer_`ve `_to_`.

> [!IMPORTANT]
> Not ettiğiniz arabirim COM ise, bu ek açıklamaların COM formunu kullanın. Diğer tür arabirimlerle COM ek açıklamalarını kullanmayın.

### <a name="annotations-and-descriptions"></a>Ek açıklamalar ve açıklamalar

- `_Outptr_result_z_`

   `_Outptr_opt_result_z_`

   `_Outptr_result_maybenull_z_`

   `_Ouptr_opt_result_maybenull_z_`

   Döndürülen işaretçinin `_Null_terminated_` ek açıklaması vardır.

- `_COM_Outptr_`

   `_COM_Outptr_opt_`

   `_COM_Outptr_result_maybenull_`

   `_COM_Outptr_opt_result_maybenull_`

   Döndürülen işaretçinin COM semantiği vardır ve bu nedenle döndürülen işaretçinin null olduğu bir `_On_failure_` koşulu taşır.

- `_Outptr_result_buffer_(s)`

   `_Outptr_result_bytebuffer_(s)`

   `_Outptr_opt_result_buffer_(s)`

   `_Outptr_opt_result_bytebuffer_(s)`

   Döndürülen işaretçi `s` öğeleri veya baytları için geçerli bir arabelleğe işaret eder.

- `_Outptr_result_buffer_to_(s, c)`

   `_Outptr_result_bytebuffer_to_(s, c)`

   `_Outptr_opt_result_buffer_to_(s,c)`

   `_Outptr_opt_result_bytebuffer_to_(s,c)`

   Döndürülen işaretçi, `s` öğeleri veya baytları için ilk `c` geçerli olduğu bir arabelleğe işaret eder.

Belirli arabirim kuralları, hata durumunda çıkış parametrelerinin null olduğunu varsayar.  Açık COM kodu hariç, aşağıdaki tablodaki formlar tercih edilir.  COM kodu için, önceki bölümde listelenen ilgili COM formlarını kullanın.

### <a name="annotations-and-descriptions"></a>Ek açıklamalar ve açıklamalar

- `_Result_nullonfailure_`

   Diğer ek açıklamaları değiştirir. İşlev başarısız olursa sonuç null olarak ayarlanır.

- `_Result_zeroonfailure_`

   Diğer ek açıklamaları değiştirir. İşlev başarısız olursa sonuç sıfır olarak ayarlanır.

- `_Outptr_result_nullonfailure_`

   Döndürülen işaretçi, işlev başarılı olursa geçerli bir arabelleğe işaret eder veya işlev başarısız olursa null olur. Bu ek açıklama isteğe bağlı olmayan bir parametre içindir.

- `_Outptr_opt_result_nullonfailure_`

   Döndürülen işaretçi, işlev başarılı olursa geçerli bir arabelleğe işaret eder veya işlev başarısız olursa null olur. Bu ek açıklama isteğe bağlı bir parametre içindir.

- `_Outref_result_nullonfailure_`

   Döndürülen işaretçi, işlev başarılı olursa geçerli bir arabelleğe işaret eder veya işlev başarısız olursa null olur. Bu ek açıklama bir başvuru parametresi içindir.

## <a name="output-reference-parameters"></a>Çıkış başvurusu parametreleri

Başvuru parametresinin ortak kullanımı çıkış parametrelerine yöneliktir.  `int&`gibi basit çıkış başvuru parametreleri için, `_Out_` doğru semantiğini sağlar.  Ancak, çıkış değeri `int *&`gibi bir işaretçisiyse, `_Outptr_ int **` gibi eşdeğer işaretçi ek açıklamaları doğru semantiğini sağlamaz.  İşaretçi türleri için çıkış başvurusu parametrelerinin semantiğini öz için, bu bileşik ek açıklamaları kullanın:

### <a name="annotations-and-descriptions"></a>Ek açıklamalar ve açıklamalar

- `_Outref_`

     Sonuç, durum sonrası için geçerli olmalıdır ve null olamaz.

- `_Outref_result_maybenull_`

     Sonuç, durum sonrası için geçerli olmalıdır, ancak durum sonrası null olabilir.

- `_Outref_result_buffer_(s)`

     Sonuç, durum sonrası için geçerli olmalıdır ve null olamaz. `s` öğeleri için geçerli arabelleğe işaret eder.

- `_Outref_result_bytebuffer_(s)`

     Sonuç, durum sonrası için geçerli olmalıdır ve null olamaz. `s` bayt boyutundaki geçerli arabelleğe işaret eder.

- `_Outref_result_buffer_to_(s, c)`

     Sonuç, durum sonrası için geçerli olmalıdır ve null olamaz. İlk `c` geçerli olduğu `s` öğelerinin arabelleğini işaret eder.

- `_Outref_result_bytebuffer_to_(s, c)`

     Sonuç, durum sonrası için geçerli olmalıdır ve null olamaz. İlk `c` geçerli olduğu `s` baytlık arabelleğe işaret eder.

- `_Outref_result_buffer_all_(s)`

     Sonuç, durum sonrası için geçerli olmalıdır ve null olamaz. Geçerli öğelerin `s` geçerli arabellek boyutunu gösterir.

- `_Outref_result_bytebuffer_all_(s)`

     Sonuç, durum sonrası için geçerli olmalıdır ve null olamaz. Geçerli öğe `s` baytlarının geçerli arabelleğini işaret eder.

- `_Outref_result_buffer_maybenull_(s)`

     Sonuç, durum sonrası için geçerli olmalıdır, ancak durum sonrası null olabilir. `s` öğeleri için geçerli arabelleğe işaret eder.

- `_Outref_result_bytebuffer_maybenull_(s)`

     Sonuç, durum sonrası için geçerli olmalıdır, ancak durum sonrası null olabilir. `s` bayt boyutundaki geçerli arabelleğe işaret eder.

- `_Outref_result_buffer_to_maybenull_(s, c)`

     Sonuç, durum sonrası için geçerli olmalıdır, ancak durum sonrası null olabilir. İlk `c` geçerli olduğu `s` öğelerinin arabelleğini işaret eder.

- `_Outref_result_bytebuffer_to_maybenull_(s,c)`

     Sonuç, durum sonrası için geçerli olmalıdır, ancak post durumunda null olabilir. İlk `c` geçerli olduğu `s` baytlık arabelleğe işaret eder.

- `_Outref_result_buffer_all_maybenull_(s)`

     Sonuç, durum sonrası için geçerli olmalıdır, ancak post durumunda null olabilir. Geçerli öğelerin `s` geçerli arabellek boyutunu gösterir.

- `_Outref_result_bytebuffer_all_maybenull_(s)`

     Sonuç, durum sonrası için geçerli olmalıdır, ancak post durumunda null olabilir. Geçerli öğe `s` baytlarının geçerli arabelleğini işaret eder.

## <a name="return-values"></a>Dönüş Değerleri

Bir işlevin dönüş değeri bir `_Out_` parametresine benzer, ancak farklı bir de başvuru düzeyindedir ve sonuç için işaretçi kavramını düşünmeniz gerekmez.  Aşağıdaki ek açıklamalar için, dönüş değeri, bir skalar, bir struct işaretçisi veya bir arabelleğin işaretçisi olan açıklamalı nesnedir. Bu ek açıklamalar karşılık gelen `_Out_` ek açıklaması ile aynı semantiğe sahiptir.

|||
|-|-|
|`_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`|`_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`|

## <a name="format-string-parameters"></a>Biçim dizesi parametreleri

- `_Printf_format_string_`, parametrenin bir `printf` ifadesinde kullanılmak üzere bir biçim dizesi olduğunu gösterir.

     **Örnek**

    ```cpp
    int MyPrintF(_Printf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwprintf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_format_string_`, parametrenin bir `scanf` ifadesinde kullanılmak üzere bir biçim dizesi olduğunu gösterir.

     **Örnek**

    ```cpp
    int MyScanF(_Scanf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_s_format_string_`, parametrenin bir `scanf_s` ifadesinde kullanılmak üzere bir biçim dizesi olduğunu gösterir.

     **Örnek**

    ```cpp
    int MyScanF_s(_Scanf_s_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf_s(format, args);
           va_end(args);
           return ret;
    }
    ```

## <a name="other-common-annotations"></a>Diğer yaygın ek açıklamalar

### <a name="annotations-and-descriptions"></a>Ek açıklamalar ve açıklamalar

- `_In_range_(low, hi)`

     `_Out_range_(low, hi)`

     `_Ret_range_(low, hi)`

     `_Deref_in_range_(low, hi)`

     `_Deref_out_range_(low, hi)`

     `_Deref_inout_range_(low, hi)`

     `_Field_range_(low, hi)`

     Parametresi, alanı veya sonucu, `hi``low` (dahil) aralığındadır.  Açıklamalı nesneye uygun ön durum veya durum sonrası koşullarıyla birlikte uygulanan `_Satisfies_(_Curr_ >= low && _Curr_ <= hi)` eşdeğerdir.

    > [!IMPORTANT]
    > Adlar "ın" ve "Out" içerse de, `_In_` ve `_Out_` semantiği bu ek açıklamalar için **uygulanmıyor.**

- `_Pre_equal_to_(expr)`

     `_Post_equal_to_(expr)`

     Açıklamalı değer tam olarak `expr`.  Açıklamalı nesneye uygun ön durum veya durum sonrası koşullarıyla birlikte uygulanan `_Satisfies_(_Curr_ == expr)` eşdeğerdir.

- `_Struct_size_bytes_(size)`

     Bir struct veya Class bildirimi için geçerlidir.  Bu türdeki geçerli bir nesnenin, `size`tarafından verilen bayt sayısıyla, belirtilen türden daha büyük olabileceğini gösterir.  Örnek:

     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`

     `MyStruct *` türündeki bir parametre `pM` arabellek boyutu daha sonra şu şekilde alınır:

     `min(pM->nSize, sizeof(MyStruct))`

## <a name="related-resources"></a>İlgili Kaynaklar

[Kod Analizi ekip blogu](https://blogs.msdn.microsoft.com/codeanalysis/)

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL'yi Anlama](../code-quality/understanding-sal.md)
- [İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)
- [Yapıları ve Sınıfları Yorumlama](../code-quality/annotating-structs-and-classes.md)
- [Kilitlenme Davranışını Yorumlama](../code-quality/annotating-locking-behavior.md)
- [Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [İç İşlevler](../code-quality/intrinsic-functions.md)
- [En İyi Yöntemler ve Örnekler](../code-quality/best-practices-and-examples-sal.md)
