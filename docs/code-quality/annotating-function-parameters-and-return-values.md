---
title: İşlev parametreleri ve iade değerleri açıklama
description: İşlev parametresi ve iade değeri ek açıklamaları için başvuru kılavuzu.
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
- _Outptr_opt_result_maybenull_z_
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
ms.openlocfilehash: c787dcfb252da1abe47251d66c46689db289cf15
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328004"
---
# <a name="annotating-function-parameters-and-return-values"></a>İşlev parametreleri ve iade değerleri açıklama

Bu makalede, basit işlev parametreleri için ek açıklamaların tipik kullanımları açıklanır(skaler ve yapılara ve sınıflara işaretçiler-ve çoğu arabellek türü. Bu makalede, ek açıklamalar için ortak kullanım desenleri de gösterilmektedir. İşlevlerle ilgili ek ek açıklamalar için [bkz.](../code-quality/annotating-function-behavior.md)

## <a name="pointer-parameters"></a>İşaretçi parametreleri

Aşağıdaki tablodaki ek açıklamalar için, işaretçi parametresi açıklama lı yken, çözümleyici işaretçi null ise bir hata bildirir. Bu ek açıklama işaretçiler ve işaret eden tüm veri öğesi için geçerlidir.

### <a name="annotations-and-descriptions"></a>Ek Açıklamalar ve açıklamalar

- `_In_`

     Skaler, yapılar, yapılar ve benzeri işaretçiler olan giriş parametrelerini açıklama. Açıkça basit skalers kullanılabilir. Parametre önceden geçerli olmalıdır ve değiştirilmez.

- `_Out_`

     Skaler, yapılar, yapılar ve benzeri işaretçiler olan çıkış parametrelerini açıklama. Bu ek açıklamayı, örneğin değer tarafından geçirilen bir skaler gibi bir değeri döndüremeyen bir nesneye uygulamayın. Parametrenin ön durum açısından geçerli olması, ancak post-state olarak geçerli olması gerekir.

- `_Inout_`

     İşlev tarafından değiştirilecek bir parametreye açıklama getirir. Hem durum öncesi hem de sonrası durum açısından geçerli olmalıdır, ancak aramadan önce ve sonra farklı değerlere sahip olduğu varsayılır. Değiştirilebilir bir değere uygulanmalıdır.

- `_In_z_`

     Giriş olarak kullanılan null-sonlandırılan dize için bir işaretçi. Dize önceden geçerli olmalıdır. Zaten doğru `PSTR`ek açıklamalara sahip olan türevleri tercih edilir.

- `_Inout_z_`

     Değiştirilecek null-sonlandırılan karakter dizisiiçin bir işaretçi. Aramadan önce ve sonra geçerli olmalıdır, ancak değerin değiştiği varsayılır. Null terminator taşınabilir, ancak yalnızca özgün null terminator kadar öğeleri erişilebilir.

- `_In_reads_(s)`

     `_In_reads_bytes_(s)`

     İşlev tarafından okunan bir diziiçin işaretçi. Dizi, tümü `s` geçerli olmalıdır boyut öğeleri, biridir.

     Varyant `_bytes_` öğeleri yerine bayt boyutu verir. Bu varyantı yalnızca boyut öğe olarak ifade edilenemediğinde kullanın. Örneğin, `char` dizeleri `_bytes_` yalnızca kullanan `wchar_t` benzer bir işlev olacaksa varyantı kullanır.

- `_In_reads_z_(s)`

     Null-sonlandırılan ve bilinen boyutu olan bir dizi için işaretçi. Null terminator'a kadar olan `s` öğeler veya null terminator yoksa, ön durum geçerli olmalıdır. Boyut baytlarda biliniyorsa, `s` öğe boyutuna göre ölçeklendirin.

- `_In_reads_or_z_(s)`

     Null-sonlandırılan veya bilinen boyutu veya her ikisi olan bir dizi için işaretçi. Null terminator'a kadar olan `s` öğeler veya null terminator yoksa, ön durum geçerli olmalıdır. Boyut baytlarda biliniyorsa, `s` öğe boyutuna göre ölçeklendirin. `strn` (Aile için kullanılır.)

- `_Out_writes_(s)`

     `_Out_writes_bytes_(s)`

     İşlev tarafından yazılacak bir `s` dizi öğeye (resp. bayt) işaretçi. Dizi öğelerinin ön durum açısından geçerli olması gerekmez ve post-state'te geçerli olan öğelerin sayısı belirtilmemiştir. Parametre türünde ek açıklamalar varsa, bunlar durum sonrası uygulanır. Örneğin, aşağıdaki kodu göz önünde bulundurun.

     ```cpp
     typedef _Null_terminated_ wchar_t *PWSTR;
     void MyStringCopy(_Out_writes_(size) PWSTR p1, _In_ size_t size, _In_ PWSTR p2);
     ```

     Bu örnekte, arayan için `size` `p1`öğelerin bir arabellek sağlar. `MyStringCopy`bu öğelerden bazılarını geçerli kılar. Daha da önemlisi, `_Null_terminated_` ek `PWSTR` açıklama, `p1` post-state'te geçersiz kılınan anlamına gelir. Bu şekilde, geçerli öğelerin sayısı hala iyi tanımlanmıştır, ancak belirli bir öğe sayısı gerekli değildir.

     Varyant `_bytes_` öğeleri yerine bayt boyutu verir. Bu varyantı yalnızca boyut öğe olarak ifade edilenemediğinde kullanın. Örneğin, `char` dizeleri `_bytes_` yalnızca kullanan `wchar_t` benzer bir işlev olacaksa varyantı kullanır.

- `_Out_writes_z_(s)`

     `s` Bir dizi öğeiçin işaretçi. Öğelerin ön durum olarak geçerli olması gerekmez. Post-state olarak, null terminator aracılığıyla elemanları -ki mevcut olmalıdır- geçerli olmalıdır. Boyut baytlarda biliniyorsa, `s` öğe boyutuna göre ölçeklendirin.

- `_Inout_updates_(s)`

     `_Inout_updates_bytes_(s)`

     İşleviçinde hem okunan hem de yazılan bir diziiçin işaretçi. Bu boyut `s` öğeleri, ve ön-devlet ve post-state geçerli.

     Varyant `_bytes_` öğeleri yerine bayt boyutu verir. Bu varyantı yalnızca boyut öğe olarak ifade edilenemediğinde kullanın. Örneğin, `char` dizeleri `_bytes_` yalnızca kullanan `wchar_t` benzer bir işlev olacaksa varyantı kullanır.

- `_Inout_updates_z_(s)`

     Null-sonlandırılan ve bilinen boyutu olan bir dizi için işaretçi. Null terminator aracılığıyla öğeleri -ki mevcut olmalıdır- hem ön durum hem de post-state geçerli olmalıdır. Post-devletteki değerin, ön durumdaki değerden farklı olduğu varsayılır; null terminatörün yerini içerir. Boyut baytlarda biliniyorsa, `s` öğe boyutuna göre ölçeklendirin.

- `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     `s` Bir dizi öğeiçin işaretçi. Öğelerin ön durum olarak geçerli olması gerekmez. Post-state'te, `c`-th öğesine kadar olan öğeler geçerli olmalıdır. Boyut, `_bytes_` eleman sayısı yerine baytolarak biliniyorsa, varyant kullanılabilir.

     Örneğin:

     ```cpp
     void *memcpy(_Out_writes_bytes_all_(s) char *p1, _In_reads_bytes_(s) char *p2, _In_ int s);
     void *wordcpy(_Out_writes_all_(s) DWORD *p1, _In_reads_(s) DWORD *p2, _In_ int s);
     ```

- `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     İşlev tarafından hem okunan hem de yazılan bir diziiçin işaretçi. Boyut `s` öğeleri, hepsi ön durum geçerli olmalıdır ve `c` öğeler post-state geçerli olmalıdır.

     Varyant `_bytes_` öğeleri yerine bayt boyutu verir. Bu varyantı yalnızca boyut öğe olarak ifade edilenemediğinde kullanın. Örneğin, `char` dizeleri `_bytes_` yalnızca kullanan `wchar_t` benzer bir işlev olacaksa varyantı kullanır.

- `_Inout_updates_all_(s)`

     `_Inout_updates_bytes_all_(s)`

     Boyut `s` öğelerinin işlevi tarafından hem okunan hem de yazılan bir diziiçin işaretçi. Eşdeğer olarak tanımlanır:

     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`

     Başka bir deyişle, ön duruma kadar `s` arabellekte bulunan her öğe, ön durum ve post-state'te geçerlidir.

     Varyant `_bytes_` öğeleri yerine bayt boyutu verir. Bu varyantı yalnızca boyut öğe olarak ifade edilenemediğinde kullanın. Örneğin, `char` dizeleri `_bytes_` yalnızca kullanan `wchar_t` benzer bir işlev olacaksa varyantı kullanır.

- `_In_reads_to_ptr_(p)`

     (yani eksi) `p - _Curr_` `p` `_Curr_`geçerli bir ifade olan bir diziiçin işaretçi. Önceki `p` öğeler önceden geçerli olmalıdır.

    Örneğin:

    ```cpp
    int ReadAllElements(_In_reads_to_ptr_(EndOfArray) const int *Array, const int *EndOfArray);
    ```

- `_In_reads_to_ptr_z_(p)`

     İfadenin `p - _Curr_` `p` (yani eksi) `_Curr_`geçerli bir ifade olduğu, geçersiz olarak sonlandırılan bir diziye işaretçi. Önceki `p` öğeler önceden geçerli olmalıdır.

- `_Out_writes_to_ptr_(p)`

     (yani eksi) `p - _Curr_` `p` `_Curr_`geçerli bir ifade olan bir diziiçin işaretçi. Önceki `p` öğelerin ön durum içinde geçerli olması ve post-state olarak geçerli olması gerekir.

- `_Out_writes_to_ptr_z_(p)`

     (yani eksi) `p - _Curr_` `p` `_Curr_`geçerli bir ifade olan geçersiz sonlandırılmış bir diziiçin işaretçi. Önceki `p` öğelerin ön durum içinde geçerli olması ve post-state olarak geçerli olması gerekir.

## <a name="optional-pointer-parameters"></a>İsteğe bağlı işaretçi parametreleri

Bir işaretçi parametre açıklama `_opt_`içeriyorsa, bu parametre null olabileceğini gösterir. Aksi takdirde, ek açıklama içermeyen `_opt_`sürümle aynı şekilde olur. İşaretçi parametre `_opt_` ek açıklamalarının türevlerinin bir listesi aşağıda veda eder:

||||
|-|-|-|
|`_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`|`_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`|`_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`|

## <a name="output-pointer-parameters"></a>Çıkış işaretçisi parametreleri

Çıkış işaretçisi parametreleri, parametre ve işaretli konumdaki nullness'i ayrıştırmak için özel gösterim gerektirir.

### <a name="annotations-and-descriptions"></a>Ek Açıklamalar ve açıklamalar

- `_Outptr_`

   Parametre null olamaz ve post-state işaretli konum null olamaz ve geçerli olmalıdır.

- `_Outptr_opt_`

   Parametre null olabilir, ancak post-state işaretli konum null olamaz ve geçerli olmalıdır.

- `_Outptr_result_maybenull_`

   Parametre null olamaz ve post-state işaretli konum null olabilir.

- `_Outptr_opt_result_maybenull_`

   Parametre null olabilir ve post-state işaretli konum null olabilir.

  Aşağıdaki tabloda, ek açıklamanın anlamını daha da nitelemek için ek açıklama adına ek alt dizeleri eklenir. Çeşitli alt dizeleri `_z` `_COM_`vardır `_buffer_` `_bytebuffer_`, `_to_`, , , ve .

> [!IMPORTANT]
> Açıklama yaptığınız arabirim COM ise, bu ek açıklamaların COM formunu kullanın. Com ek açıklamalarını başka bir tür arabirimiyle kullanmayın.

- `_Outptr_result_z_`

   `_Outptr_opt_result_z_`

   `_Outptr_result_maybenull_z_`

   `_Outptr_opt_result_maybenull_z_`

   Döndürülen işaretçiek açıklama vardır. `_Null_terminated_`

- `_COM_Outptr_`

   `_COM_Outptr_opt_`

   `_COM_Outptr_result_maybenull_`

   `_COM_Outptr_opt_result_maybenull_`

   Döndürülen işaretçi COM semantikleri vardır `_On_failure_` ve bu nedenle döndürülen işaretçinin null olması koşulu taşır.

- `_Outptr_result_buffer_(s)`

   `_Outptr_result_bytebuffer_(s)`

   `_Outptr_opt_result_buffer_(s)`

   `_Outptr_opt_result_bytebuffer_(s)`

   Döndürülen işaretçi, boyut `s` öğeleri veya baytların geçerli bir arabelleği işaret eder.

- `_Outptr_result_buffer_to_(s, c)`

   `_Outptr_result_bytebuffer_to_(s, c)`

   `_Outptr_opt_result_buffer_to_(s,c)`

   `_Outptr_opt_result_bytebuffer_to_(s,c)`

   Döndürülen işaretçi, ilki `s` `c` geçerli olan boyut öğeleri veya baytarasını işaret eder.

Bazı arabirim kuralları, çıktı parametrelerinin hata da geçersiz kılındığını varsayılmaktadır. Açıkça COM kodu dışında, aşağıdaki tablodaki formlar tercih edilir. COM kodu için, önceki bölümde listelenen ilgili COM formlarını kullanın.

- `_Result_nullonfailure_`

   Diğer ek açıklamaları değiştirir. İşlev başarısız olursa sonuç null ayarlanır.

- `_Result_zeroonfailure_`

   Diğer ek açıklamaları değiştirir. İşlev başarısız olursa sonuç sıfıra ayarlanır.

- `_Outptr_result_nullonfailure_`

   Döndürülen işaretçi, işlev başarılı olursa geçerli bir arabelleğe veya işlev başarısız olursa geçersiz kılınmasını sağlar. Bu ek açıklama isteğe bağlı olmayan bir parametre içindir.

- `_Outptr_opt_result_nullonfailure_`

   Döndürülen işaretçi, işlev başarılı olursa geçerli bir arabelleğe veya işlev başarısız olursa geçersiz kılınmasını sağlar. Bu ek açıklama isteğe bağlı bir parametre içindir.

- `_Outref_result_nullonfailure_`

   Döndürülen işaretçi, işlev başarılı olursa geçerli bir arabelleğe veya işlev başarısız olursa geçersiz kılınmasını sağlar. Bu ek açıklama bir başvuru parametresi içindir.

## <a name="output-reference-parameters"></a>Çıkış referans parametreleri

Başvuru parametresinin yaygın kullanımı çıkış parametreleri içindir. Basit çıktı referans parametreleri için `int&`, `_Out_` doğru semantik sağlar. Ancak, çıktı değeri gibi `int *&`bir işaretçi olduğunda , eşdeğer `_Outptr_ int **` işaretçi ek açıklamaları doğru semantik sağlamaz. İşaretçi türleri için çıktı başvuru parametrelerinin anlamsallarını kısaca ifade etmek için şu bileşik ek açıklamaları kullanın:

### <a name="annotations-and-descriptions"></a>Ek Açıklamalar ve açıklamalar

- `_Outref_`

     Sonuç post-state geçerli olmalıdır ve null olamaz.

- `_Outref_result_maybenull_`

     Sonuç post-state geçerli olmalıdır, ancak post-state geçersiz olabilir.

- `_Outref_result_buffer_(s)`

     Sonuç post-state geçerli olmalıdır ve null olamaz. Boyut `s` öğelerinin geçerli arabelleği için puan.

- `_Outref_result_bytebuffer_(s)`

     Sonuç post-state geçerli olmalıdır ve null olamaz. Boyut `s` baytlarının geçerli arabelleği ne işaret eder.

- `_Outref_result_buffer_to_(s, c)`

     Sonuç post-state geçerli olmalıdır ve null olamaz. İlki `c` geçerli `s` olan öğelerin arabelleği ne kadar noktalar.

- `_Outref_result_bytebuffer_to_(s, c)`

     Sonuç post-state geçerli olmalıdır ve null olamaz. İlki `c` geçerli `s` olan bayt arabelleği için noktalar.

- `_Outref_result_buffer_all_(s)`

     Sonuç post-state geçerli olmalıdır ve null olamaz. Boyut `s` geçerli öğelerinin geçerli arabelleği için puan.

- `_Outref_result_bytebuffer_all_(s)`

     Sonuç post-state geçerli olmalıdır ve null olamaz. Geçerli öğelerin baytlarının `s` geçerli arabelleği için puan.

- `_Outref_result_buffer_maybenull_(s)`

     Sonuç post-state geçerli olmalıdır, ancak post-state geçersiz olabilir. Boyut `s` öğelerinin geçerli arabelleği için puan.

- `_Outref_result_bytebuffer_maybenull_(s)`

     Sonuç post-state geçerli olmalıdır, ancak post-state geçersiz olabilir. Boyut `s` baytlarının geçerli arabelleği ne işaret eder.

- `_Outref_result_buffer_to_maybenull_(s, c)`

     Sonuç post-state geçerli olmalıdır, ancak post-state geçersiz olabilir. İlki `c` geçerli `s` olan öğelerin arabelleği ne kadar noktalar.

- `_Outref_result_bytebuffer_to_maybenull_(s,c)`

     Sonuç post-state geçerli olmalıdır, ancak posta durumunda geçersiz olabilir. İlki `c` geçerli `s` olan bayt arabelleği için noktalar.

- `_Outref_result_buffer_all_maybenull_(s)`

     Sonuç post-state geçerli olmalıdır, ancak posta durumunda geçersiz olabilir. Boyut `s` geçerli öğelerinin geçerli arabelleği için puan.

- `_Outref_result_bytebuffer_all_maybenull_(s)`

     Sonuç post-state geçerli olmalıdır, ancak posta durumunda geçersiz olabilir. Geçerli öğelerin baytlarının `s` geçerli arabelleği için puan.

## <a name="return-values"></a>Döndürülen değerler

Bir işlevin geri dönüş `_Out_` değeri bir parametreye benzer, ancak farklı bir başvuru düzeyindedir ve sonuç işaretçisi kavramını göz önünde bulundurmanız gerekir. Aşağıdaki ek açıklamalar için, iade değeri açıklamalı nesnedir-bir skaler, bir yapı için işaretçi veya arabellek için bir işaretçi. Bu ek açıklamalar, ilgili `_Out_` ek açıklamayla aynı anlambilime sahiptir.

|||
|-|-|
|`_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`|`_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`|

## <a name="format-string-parameters"></a>Biçim dize parametreleri

- `_Printf_format_string_`Parametrenin bir `printf` ifadede kullanılmak üzere bir biçim dizesi olduğunu gösterir.

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

- `_Scanf_format_string_`Parametrenin bir `scanf` ifadede kullanılmak üzere bir biçim dizesi olduğunu gösterir.

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

- `_Scanf_s_format_string_`Parametrenin bir `scanf_s` ifadede kullanılmak üzere bir biçim dizesi olduğunu gösterir.

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

## <a name="other-common-annotations"></a>Diğer ortak ek açıklamalar

### <a name="annotations-and-descriptions"></a>Ek Açıklamalar ve açıklamalar

- `_In_range_(low, hi)`

     `_Out_range_(low, hi)`

     `_Ret_range_(low, hi)`

     `_Deref_in_range_(low, hi)`

     `_Deref_out_range_(low, hi)`

     `_Deref_inout_range_(low, hi)`

     `_Field_range_(low, hi)`

     Parametre, alan veya sonuç aralıkta (dahil) `low` `hi`dan . `_Satisfies_(_Curr_ >= low && _Curr_ <= hi)` Buna eşdeğer uygun ön durum veya post-state koşulları ile birlikte açıklamalı nesneye uygulanır.

    > [!IMPORTANT]
    > Adlar "in" ve "out" içerse `_In_` de, bu ek açıklamalar için anlamsal ve `_Out_` **geçerli değildir.**

- `_Pre_equal_to_(expr)`

     `_Post_equal_to_(expr)`

     Açıklamalı değer tam olarak. `expr` `_Satisfies_(_Curr_ == expr)` Buna eşdeğer uygun ön durum veya post-state koşulları ile birlikte açıklamalı nesneye uygulanır.

- `_Struct_size_bytes_(size)`

     Bir yapı veya sınıf bildirimi için geçerlidir. Bu tür geçerli bir nesnenin, `size`bayt sayısı nın verildiği, beyan edilen türden daha büyük olabileceğini gösterir. Örneğin:

     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`

     Bir tür `pM` `MyStruct *` parametrenin baytlarında arabellek boyutu daha sonra aşağıdaki şekilde alınır:

     `min(pM->nSize, sizeof(MyStruct))`

## <a name="related-resources"></a>İlgili kaynaklar

[Kod Analizi Takım Blog](https://blogs.msdn.microsoft.com/codeanalysis/)

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL'ı Anlama](../code-quality/understanding-sal.md)
- [İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)
- [Yapıları ve Sınıfları Yorumlama](../code-quality/annotating-structs-and-classes.md)
- [Kilitlenme Davranışını Yorumlama](../code-quality/annotating-locking-behavior.md)
- [Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [İç İşlevler](../code-quality/intrinsic-functions.md)
- [En İyi Yöntemler ve Örnekler](../code-quality/best-practices-and-examples-sal.md)
