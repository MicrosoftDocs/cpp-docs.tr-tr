---
description: 'Hakkında daha fazla bilgi edinin: En Iyi Yöntemler ve örnekler (SAL)'
title: En İyi Yöntemler ve Örnekler (SAL)
ms.date: 11/04/2016
ms.topic: conceptual
ms.openlocfilehash: d252f019637aa65aacb0bcfd7e924d94bda0d400
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97279604"
---
# <a name="best-practices-and-examples-sal"></a>En İyi Yöntemler ve Örnekler (SAL)

Kaynak kodu ek açıklama dilinden (SAL) en iyi şekilde yararlanmak ve bazı yaygın sorunlardan kaçınmak için bazı yollar aşağıda verilmiştir.

## <a name="_in_"></a>\_İçinde\_

İşlevin öğesine yazılması gerekiyorsa, `_Inout_` yerine kullanın `_In_` . Bu özellikle, eski makrolardan SAL 'a otomatik dönüştürme gibi durumlar için geçerlidir. Sal 'tan önce birçok programcı, `IN` Bu adların adı,, `OUT` veya varyantları olarak adlandırılan makrolar açıklama olarak kullanılmıştır `IN_OUT` . Bu makroları SAL 'a dönüştürmenizi öneririz; ancak, özgün prototip yazıldığı ve eski makro artık kodun ne yaptığını yansıtmadığından, bu makroları dönüştürme işlemi için de dikkatli olabilirsiniz. `OPTIONAL`Genellikle doğru şekilde yerleştirildiğinden (örneğin, bir virgülden oluşan yanlış tarafta) yorum makrosu hakkında özellikle dikkatli olun.

```cpp

// Incorrect
void Func1(_In_ int *p1)
{
    if (p1 == NULL)
        return;

    *p1 = 1;
}

// Correct
void Func2(_Inout_ PCHAR p1)
{
    if (p1 == NULL)
        return;

    *p1 = 1;
}
```

## <a name="_opt_"></a>\_opt\_

Çağıranın null bir işaretçiye geçmesine izin verilmiyorsa, `_In_` `_Out_` veya yerine kullanın `_In_opt_` `_Out_opt_` . Bu, parametrelerini denetleyen ve olmaması gerektiğinde NULL olduğunda bir hata döndüren bir işlev için de geçerlidir. Bir işleve sahip olmak, parametresini beklenmeyen NULL için kontrol edin ve düzgün bir savunma kodlama uygulaması olsa da, parametre ek açıklamanın isteğe bağlı bir tür ( `_*Xxx*_opt_` ) olabilir.

```cpp

// Incorrect
void Func1(_Out_opt_ int *p1)
{
    *p = 1;
}

// Correct
void Func2(_Out_ int *p1)
{
    *p = 1;
}
```

## <a name="_pre_defensive_-and-_post_defensive_"></a>\_Ön \_ savunma \_ ve \_ gönderi \_ savunlayıcı\_

Bir işlev güven sınırında görünürse, `_Pre_defensive_` ek açıklamayı kullanmanızı öneririz.  "Savunma" değiştiricisi belirli ek açıklamaları değiştirerek, çağrı noktasında arabirimin kesinlikle denetlenmesi gerektiğini, ancak uygulama gövdesinde yanlış parametrelerin geçirildiğine yönelik olduğunu varsaymalıdır. Bu durumda, `_In_ _Pre_defensive_` bir arayan bir hata, null geçirmeye çalışırsa bir hata edineceği için bir güven sınırında tercih edilir. işlev gövdesi, parametre null olabilir ve işaretçi ilk olarak null olarak denetlenmeden bu işaretçiye başvuruda bulunmak için denemeler işaretlenir.  `_Post_defensive_`Güvenilen tarafın arayan olarak kabul edildiği ve güvenilmeyen kodun çağrılan kod olduğu geri aramalarda kullanılmak üzere ek açıklama da kullanılabilir.

## <a name="_out_writes_"></a>\_Dışarı \_ yazma işlemleri\_

Aşağıdaki örnek, öğesinin ortak bir kötüye kullanımını gösterir `_Out_writes_` .

```cpp

// Incorrect
void Func1(_Out_writes_(size) CHAR *pb,
    DWORD size
);
```

Ek açıklama, `_Out_writes_` bir arabelleğe sahip olduğunuz anlamına gelir. `cb`Çıkış sırasında başlatılan ilk bayt ile ayrılmış baytları vardır. Bu ek açıklama kesinlikle yanlış değildir ve ayrılan boyutu ifade etmek faydalı olur. Ancak, işlev tarafından kaç öğe başlatıldığını söylemez.

Sonraki örnekte, arabelleğin başlatılmış bölümünün tam boyutunu tam olarak belirtmek için üç doğru yol gösterilmektedir.

```cpp

// Correct
void Func1(_Out_writes_to_(size, *pCount) CHAR *pb,
    DWORD size,
    PDWORD pCount
);

void Func2(_Out_writes_all_(size) CHAR *pb,
    DWORD size
);

void Func3(_Out_writes_(size) PSTR pb,
    DWORD size
);
```

## <a name="_out_-pstr"></a>\_Çıkış \_ PSTR

Kullanımı `_Out_ PSTR` neredeyse her zaman yanlıştır. Bu, bir karakter arabelleğini işaret eden bir çıkış parametresine sahip olarak yorumlanır ve NULL olarak sonlandırılır.

```cpp

// Incorrect
void Func1(_Out_ PSTR pFileName, size_t n);

// Correct
void Func2(_Out_writes_(n) PSTR wszFileName, size_t n);
```

Benzer bir ek açıklama `_In_ PCSTR` yaygın ve kullanışlı bir seçenektir. Önkoşul, `_In_` null ile sonlandırılmış bir dizenin tanınmasını sağladığından, null sonlandırmasına sahip bir giriş dizesini işaret eder.

## <a name="_in_-wchar-p"></a>\_\_Wchar * p 'de

`_In_ WCHAR* p` bir karakteri işaret eden bir giriş işaretçisi olduğunu söyler `p` . Ancak çoğu durumda bu, amaçlanan belirtim olabilir. Bunun yerine, büyük olasılıkla amaçlanan, NULL ile sonlandırılmış bir dizinin belirtimidir; Bunu yapmak için kullanın `_In_ PWSTR` .

```cpp

// Incorrect
void Func1(_In_ WCHAR* wszFileName);

// Correct
void Func2(_In_ PWSTR wszFileName);
```

NULL sonlandırmanın doğru belirtimi eksik. `STR`Aşağıdaki örnekte gösterildiği gibi, türü değiştirmek için uygun sürümü kullanın.

```cpp

// Incorrect
BOOL StrEquals1(_In_ PCHAR p1, _In_ PCHAR p2)
{
    return strcmp(p1, p2) == 0;
}

// Correct
BOOL StrEquals2(_In_ PSTR p1, _In_ PSTR p2)
{
    return strcmp(p1, p2) == 0;
}
```

## <a name="_out_range_"></a>\_Out \_ aralığı\_

Parametresi bir işaretçisiyse ve işaretçi tarafından işaret edilen öğenin değer aralığını ifade etmek istiyorsanız `_Deref_out_range_` yerine kullanın `_Out_range_` . Aşağıdaki örnekte, * Pcbdoldurulmuş aralığı, Pcbdoldurulmuş değil ifade edilir.

```cpp

// Incorrect
void Func1(
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,
    DWORD cbSize,
    _Out_range_(0, cbSize) DWORD *pcbFilled
);

// Correct
void Func2(
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,
    DWORD cbSize,
    _Deref_out_range_(0, cbSize) _Out_ DWORD *pcbFilled
);
```

`_Deref_out_range_(0, cbSize)` , ' den çıkarsanabileceğinden bazı araçlar için kesinlikle gerekli değildir `_Out_writes_to_(cbSize,*pcbFilled)` , ancak bu, tamamlanma açısından burada gösterilmiştir.

## <a name="wrong-context-in-_when_"></a>Sırasında yanlış bağlam \_\_

Diğer bir yaygın hata, ön koşullar için durum sonrası değerlendirme kullanmaktır. Aşağıdaki örnekte, `_Requires_lock_held_` önkoşuludur.

```cpp

// Incorrect
_When_(return == 0, _Requires_lock_held_(p->cs))
int Func1(_In_ MyData *p, int flag);

// Correct
_When_(flag == 0, _Requires_lock_held_(p->cs))
int Func2(_In_ MyData *p, int flag);
```

İfade, `result` ön durum ' da kullanılamayan bir durum sonrası değeri ifade eder.

## <a name="true-in-_success_"></a>Başarı durumunda doğru \_\_

Dönüş değeri sıfır olmadığında işlev başarılı olursa, `return != 0` yerine başarı koşulu olarak kullanın `return == TRUE` . Sıfır olmayan değerin, derleyicinin sağladığı gerçek değere eşdeğer olması gerekmez `TRUE` . Parametresi `_Success_` bir ifadedir ve aşağıdaki ifadeler eşdeğer olarak değerlendirilir: `return != 0` ,, `return != false` `return != FALSE` , ve `return` parametresiz veya karşılaştırmalar yok.

```cpp
// Incorrect
_Success_(return == TRUE) _Acquires_lock_(*lpCriticalSection)
BOOL WINAPI TryEnterCriticalSection(
  _Inout_ LPCRITICAL_SECTION lpCriticalSection
);

// Correct
_Success_(return != 0) _Acquires_lock_(*lpCriticalSection)
BOOL WINAPI TryEnterCriticalSection(
  _Inout_ LPCRITICAL_SECTION lpCriticalSection
);
```

## <a name="reference-variable"></a>Başvuru değişkeni

Bir başvuru değişkeni için, SAL 'un önceki sürümü, kapsanan işaretçiyi ek açıklama hedefi olarak kullandı ve bir `__deref` başvuru değişkenine eklenmiş olan ek açıklamaların eklenmesini gerektiriyordu. Bu sürüm nesnenin kendisini kullanır ve ek gerektirmez `_Deref_` .

```cpp

// Incorrect
void Func1(
    _Out_writes_bytes_all_(cbSize) BYTE *pb,
    _Deref_ _Out_range_(0, 2) _Out_ DWORD &cbSize
);

// Correct
void Func2(
    _Out_writes_bytes_all_(cbSize) BYTE *pb,
    _Out_range_(0, 2) _Out_ DWORD &cbSize
);
```

## <a name="annotations-on-return-values"></a>Dönüş değerlerinde ek açıklamalar

Aşağıdaki örnek, dönüş değeri ek açıklamalarıyla ilgili yaygın bir sorunu gösterir.

```cpp

// Incorrect
_Out_opt_ void *MightReturnNullPtr1();

// Correct
_Ret_maybenull_ void *MightReturnNullPtr2();
```

Bu örnekte, `_Out_opt_` önkoşulun bir parçası olarak IŞARETÇININ null olabileceğini belirtir. Ancak, Önkoşullar dönüş değerine uygulanamaz. Bu durumda, doğru ek açıklama olur `_Ret_maybenull_` .

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)  
[SAL'ı Anlama](../code-quality/understanding-sal.md)  
[İşlev Parametrelerini ve Dönüş Değerlerini Açıklama](../code-quality/annotating-function-parameters-and-return-values.md)  
[İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)  
[Yapıları ve Sınıfları Yorumlama](../code-quality/annotating-structs-and-classes.md)  
[Kilitlenme Davranışını Yorumlama](../code-quality/annotating-locking-behavior.md)  
[Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)  
[İç Işlevler](../code-quality/intrinsic-functions.md)
