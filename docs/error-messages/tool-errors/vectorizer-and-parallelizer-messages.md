---
title: Vektör yapıcı ve paralel hale getirici iletileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C5011
- C5002
- C5021
- C5001
- C5012
dev_langs:
- C++
ms.assetid: d8f4844a-f414-42ab-b9a5-925a5da9d365
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13067d12d2f8366f46284034589091eca188f2b1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059972"
---
# <a name="vectorizer-and-parallelizer-messages"></a>Vektör Yapıcı ve Paralel Hale Getirici İletileri

Visual C++ derleyici seçeneklerini kullanabilirsiniz [/Qpar-report](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md) ve [/Qvec-report](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md) ayarlanacak [otomatik Paralelleştirme ve otomatik Vektörleştirme](../../parallel/auto-parallelization-and-auto-vectorization.md) çıkış neden kodları için ve kendi etkinliğiyle ilgili bilgi iletileri. Bu makalede, neden kodları ve iletiler açıklanmaktadır.

- [Bilgilendirme iletileri](#BKMK_InformationalMessages)

- [5XX](#BKMK_ReasonCode50x)

- [10xx](#BKMK_ReasonCode100x)

- [11xx](#BKMK_ReasonCode110x)

- [12xx](#BKMK_ReasonCode120x)

- [13xx](#BKMK_ReasonCode130x)

- [14xx](#BKMK_ReasonCode140x)

- [15xx](#BKMK_ReasonCode150x)

##  <a name="BKMK_InformationalMessages"></a> Bilgilendirme iletileri

Belirttiğiniz raporlama düzeyine bağlı olarak, aşağıdaki bilgi iletilerinin biri her döngü için görünür.

Neden kodları hakkında daha fazla bilgi için bu makalenin sonraki bölümüne bakın.

|Bilgi İletisi|Açıklama|
|---------------------------|-----------------|
|5001|Döngü vektörleştirildi.|
|5002|Döngü 'açıklaması' nedeniyle vektörleştirilmedi.|
|5011|Döngü paralelleştirildi.|
|5012|Döngü 'açıklaması' nedeniyle paralelleştirilmedi.|
|5021|Döngü pragma ile ilişkilendirilemedi.|

## <a name="reason-codes"></a>Neden Kodları

Aşağıdaki bölümlerde, otomatik paralel hale getirici ve otomatik vektör hale getirici için olası neden kodları listelenmiştir.

###  <a name="BKMK_ReasonCode50x"></a> 5XX

5*xx* neden kodları otomatik paralel hale getirici ve otomatik vektör hale getirici için geçerlidir.

|Neden Kodu|Açıklama|
|-----------------|-----------------|
|500|Bu bazı durumları kapsayan genel bir iletidir (örneğin, döngü birden fazla çıkış içeriyor ya da döngü üstbilgisi endüksiyon değişkeninin artışıyla bitmiyor).|
|501|Endüksiyon değişkeni yerel değildir veya bir üst sınır döngü değişmez bir değer değil.|
|502|Endüksiyon değişkenine basit + 1 dışındaki bir şekilde girilmiştir.|
|503|Döngü, özel durum işleme veya anahtar ifadeleri içerir.|
|504|Döngünün gövdesi C++ nesnesinin yok edilmesini gerektiren bir özel durum oluşturabilir.|

```cpp
void code_500(int *A)
{
    // Code 500 is emitted if the loop has non-vectorizable flow.
    // This can include "if", "break", "continue", the conditional
    // operator "?", or function calls.
    // It also encompasses correct definition and use of the induction
    // variable "i", in that the increment "++i" or "i++" must be the last
    // statement in the loop.

    int i = 0;
    while (i<1000)
    {
        if (i == 4)
        {
            break;
        }

        ++i;

        A[i] = A[i] + 1;
    }
    // To resolve code 500, use a 'for' loop with single increment of
    // induction variable.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

int bound();
void code_501_example1(int *A)
{
    // Code 501 is emitted if the compiler cannot discern the
    // induction variable of this loop. In this case, when it checks
    // the upperbound of 'i', the compiler cannot prove that the
    // function call "bound()" returns the same value each time.
    // Also, the compiler cannot prove that the call to "bound()"
    // does not modify the values of array A.

    for (int i=0; i<bound(); ++i)
    {
        A[i] = A[i] + 1;
    }

    // To resolve code 501, ensure that the induction variable is
    // a local variable, and ensure that the upperbound is a
    // provably loop invariant value.

    for (int i=0, imax = bound(); i<imax; ++i)
    {
        A[i] = A[i] + 1;
    }
}

int i;
void code_501_example2(int *A)
{
    // Code 501 is emitted if the compiler cannot discern the
    // induction variable of this loop. In this case, 'i' is
    // a global.

    for (i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }

    // To resolve code 501, ensure that the induction variable is
    // a local variable, and ensure that the upperbound is a
    // provably loop invariant value.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

void code_502(int *A)
{
    // Code 502 is emitted if the compiler cannot discern
    // the induction variable of the loop. In this case,
    // there are three increments to "i", one of which
    // is conditional.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
        ++i;

        if (i < 100)
        {
            ++i;
        }
    }

    // To resolve code 502, ensure that there is just one
    // increment of the induction variable, placed in the usual
    // spot in the "for" loop.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

void code_503(int *A, int x)
{
    // Code 503 is emitted if there are inadmissible
    // operations in the loop - for example, exception handling and
    // switch statements.

    for (int i = 0; i<1000; ++i)
    {
        switch (x)
        {
        case 1: A[i] = A[i] + 1;
        case 2: A[i] = A[i] + 2;
        case 3: A[i] = A[i] + 3;
            break;
        }
    }

    // To resolve code 503, try to remove as many switch statements
    // and exception handling constructs as possible.
}

// compile with /EHsc

int code_504_helper();
class C504
{
public:
    C504();
    ~C504();
};

void code_504(int *A) {
    // Code 504 is emitted if a C++ object was created and
    // that object requires EH unwind tracking information under
    // /EHs or /EHsc.

    for(int i = 0; i < 1000; ++i)
    {
        C504 c;
        A[i] = code_504_helper();
    }

}

```

###  <a name="BKMK_ReasonCode100x"></a> 10xx

10*xx* neden kodları otomatik paralel hale getirici için geçerlidir.

|Neden Kodu|Açıklama|
|-----------------|-----------------|
|1000|Derleyici, döngü gövdesinde veri bağımlılığı algıladı.|
|1001|Derleyici döngü gövdesinde skalar bir değişken için depo algıladı ve bu skalar döngü ötesinde bir kullanıma sahip.|
|1002|Derleyici, daha önce paralel hale getirilmiş bir iç döngüye sahip bir döngüyü paralel hale getirmeyi denedi.|
|1003|Döngü gövdesi, belleğe okunabilen ya da yazılabilen bir iç çağrı içeriyor.|
|1004|Döngü gövdesinde skalar bir azalma var. Döngü vektörleştirildiğinde skalar azalma meydana gelebilir.|
|1005|**No_parallel** pragma belirtildi.|
|1006|Bu işlevi içeren **openmp**. Bu herhangi kaldırarak bunu çözebilirsiniz **openmp** Bu işlevde.|
|1007|Döngü endüksiyon değişkeni veya döngü sınırları imzalanmış 32 bitlik sayılar değil (`int` veya `long`). Endüksiyon değişkeninin türünü değiştirerek sorunu çözebilirsiniz.|
|1008|Derleyici, bu döngünün otomatik paralel hale getirmeyi garanti altına almak için yeterli ölçüde çalışmadığını algıladı.|
|1009|Derleyici, "do-while" döngüsünü paralel hale getirme denemesi algıladı. Otomatik paralel hale getirici hedefler `for` döngüleri.|
|1010|Derleyici, döngü "eşit değil" kullandığını algıladı. (! =), koşul için.|

```cpp
int A[1000];
void func();
void code_1000()
{
    // Code 1000 is emitted if the compiler detects a
    // data dependence in the loop body.

    // You can resolve this by using the ivdep pragma.
    // CAUTION -- the compiler will trust your
    // assertion that there are no data dependencies
    // in the loop body. If there are, you are generating
    // code that may have race conditions.

#pragma loop(hint_parallel(0))
    //#pragma loop(ivdep) // ivdep will force this through.
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i-1] + 1;  // data dependence here
        func();             // data dependence here
    }
}

int code_1001()
{
    // Code 1001 is emitted if the compiler detects
    // a store to a scalar variable in the loop
    // body, and that scalar has a use beyond the loop.

    // Resolve this by rewriting your code so
    // that the scalar is not needed.

    int s = 0;
#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i)
    {
        s = A[i];
    }
    return s;
}

void code_1002()
{
    // Code 1002 is emitted when the compiler tries to
    // parallelize a loop that has an inner loop that
    // has already been parallelized.

#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i) // emit code 1002 for this loop
    {
#pragma loop(hint_parallel(0))
        for (int j=0; j<1000; ++j) // this loop gets parallelized
        {
            A[j] = A[j] + 1;
        }
    }
}

extern "C" void __stosb(unsigned char*, unsigned char, size_t);
void code_1003(unsigned char *dst)
{
    // Code 1003 is emitted when the loop body contains an intrinsic
    // call that may read or write to memory.

    // This can be resolved by using the ivdep pragma.
    // CAUTION -- the compiler will trust your
    // assertion that there are no data dependencies
    // in the loop body. If there are, you are generating
    // code that may have race conditions.

#pragma loop(hint_parallel(0))
    //#pragma loop(ivdep) // ivdep will force this through.
    for (int i=0; i<1000; ++i)
    {
        __stosb(dst, 'c', 10);
        A[i] = A[i] + 1;
    }
}

int code_1004()
{
    // Code 1004 is emitted when there is a scalar reduction
    // in the loop body, which can occur if the loop has been
    // vectorized.

    // You can resolve this by rewriting your code so that it
    // does not have a scalar reduction.

    int s = 0;
#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i)
    {
        s += A[i];
    }
    return s;
}

void code_1005()
{
    // Code 1005 is emitted when the
    // no_parallel pragma is specified.

#pragma loop(no_parallel)
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

#include <omp.h>

// Compile with /openmp
void code_1006()
{
    // Code 1006 is emitted when this function contains
    // openmp. Resolve this by removing any openmp in this
    // function.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }

#pragma omp parallel num_threads(4)
    {
        int i = omp_get_thread_num();
        A[i] = A[i] + 1;
    }
}

void code_1007()
{
    // Code 1007 is emitted when the loop induction variable
    // or the loop bounds are not signed 32-bit numbers (int
    // or long). Resolve this by changing the type of the
    // induction variable.

#pragma loop(hint_parallel(0))
    for (unsigned int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

void code_1008()
{
    // Code 1008 is emitted when the compiler detects that
    // this loop does not perform enough work to warrant
    // auto-parallelization.

    // You can resolve this by specifying the hint_parallel
    // pragma. CAUTION -- if the loop does not perform
    // enough work, parallelizing might cause a potentially
    // large performance penalty.

    // #pragma loop(hint_parallel(0)) //  hint_parallel will force this through
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

void code_1009()
{
    // Code 1009 is emitted when the compiler tries to parallelize a
    // "do-while" loop. The auto-parallelizer only targets "for" loops.

    int i = 0;
#pragma loop(hint_parallel(0))
    do
    {
        A[i] = A[i] + 1;
    }
    while (++i < 1000);
}

void code_1010()
{
    // Code 1010 is emitted when the compiler tries to parallelize a
    // loop with a condition code of "!=".

    // You can resolve this by replacing it with an ordering comparator
    // like "<".
#pragma loop(hint_parallel(0))
    for (int i = 0; i != 1000; ++i)
    {
        A[i]++;
    }
}

```

###  <a name="BKMK_ReasonCode110x"></a> 11xx

11*xx* neden kodları otomatik vektör hale getirici için geçerlidir.

|Neden Kodu|Açıklama|
|-----------------|-----------------|
|1100|Döngü denetim akışı içeriyor (ör. "eğer" veya "?").|
|1101|Döngü, vektörleştirilemeyen veri türü dönüştürmesi (belki örtülü) içeriyor.|
|1102|Döngü aritmetik olmayan veya diğer vektörleştirilemeyen işlemler içeriyor.|
|1103|Döngü gövdesi, boyutu döngü içinde değişebilen kaydırma işleçleri içeriyor.|
|1104|Döngünün gövdesi skalar değişkenler içerir.|
|1105|Döngü tanınmayan azaltma işlemi içeriyor.|
|1106|Dış döngü vektörleştirilmedi.|

```cpp
void code_1100(int *A, int x)
{
    // Code 1100 is emitted when the compiler detects control flow
    // in the loop - for example, "if", the ternary operator "?", and
    // the like. Resolve this by flattening or removing control
    // flow in the loop body.

    // Not all control flow causes 1100; some is indeed
    // vectorized.

    for (int i=0; i<1000; ++i)
    {
        // straightline code is more amenable to vectorization
        if (x)
        {
            A[i] = A[i] + 1;
        }
    }
}

extern "C" int __readcr0();
void code_1102(int *A)
{
    // Code 1102 is emitted when the compiler is unable to vectorize
    // an operation in the loop body. For example, intrinsics and other
    // non-arithmetic, non-logical, and non-memory operations are not
    // vectorizable.

    // Resolve this by removing as many non-vectorizable operations
    // as possible from the loop body.

    for (int i=0; i<1000; ++i)
    {
        A[i] = __readcr0();
    }
}

void code_1103(int *A, int *B)
{
    // Code 1103 is emitted when the compiler is unable to vectorize
    // a "shift" operation. In this example, there are two shifts
    // that cannot be vectorized.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] >> B[i]; // not vectorizable

        int x = B[i];
        A[i] = A[i] >> x; // not vectorizable
    }

    // To resolve this, ensure that your shift amounts are loop
    // invariant. If the shift amounts cannot be loop invariant,
    // it may not be possible to vectorize this loop.

    int x = B[0];
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] >> x; // vectorizable
    }
}

int code_1104(int *A, int *B)
{
    // When it vectorizes a loop, the compiler must 'expand' scalar
    // variables to a vector size such that they can fit in
    // vector registers. Code 1104 is emitted when the compiler
    // cannot 'expand' such scalars.

    // In this example, we try to 'expand' x to be used in the
    // vectorized loop. However, there is a use of 'x'
    // beyond the loop body, which prohibits this expansion.

    // To resolve this, try to limit scalars to be used only in
    // the loop body and not beyond, and try to keep their types
    // consistent with the loop types.

    int x;
    for (int i=0; i<1000; ++i)
    {
        x = B[i];
        A[i] = A[i] + x;
    }

    return x;
}

int code_1105(int *A)
{
    // The compiler performs an optimization that's known as "reduction"
    // when it operates on each element of an array and computes
    // a resulting scalar value - for example, in this piece of code, which
    // computes the sum of each element in the array:

    int s = 0;
    for (int i=0; i<1000; ++i)
    {
        s += A[i]; // vectorizable
    }

    // The reduction pattern must resemble the loop in the example. The
    // compiler emits code 1105 if it cannot deduce the reduction
    // pattern, as shown in this example:

    for (int i=0; i<1000; ++i)
    {
        s += A[i] + s;  // code 1105
    }

    // Similarly, reductions of "float" or "double" types require
    // that the /fp:fast switch is thrown. Strictly speaking,
    // the reduction optimization that the compiler performs uses
    // "floating point reassociation". Reassociation is only
    // allowed when /fp:fast is thrown.

    return s;
}

void code_1106(int *A)
{
    // Code 1106 is emitted when the compiler tries to vectorize
    // an outer loop.

    for (int i=0; i<1000; ++i) // this loop is not vectorized
    {
        for (int j=0; j<1000; ++j) // this loop is vectorized
        {
            A[j] = A[j] + 1;
        }
    }
}

```

###  <a name="BKMK_ReasonCode120x"></a> 12xx

12*xx* neden kodları otomatik vektör hale getirici için geçerlidir.

|Neden Kodu|Açıklama|
|-----------------|-----------------|
|1200|Döngü, vektörleşmeyi önleyen, döngüyle taşınan veri bağımlılıkları içeriyor. Döngünün farklı yinelemeleri birbiriyle etkileşiyor ve bu nedenle de döngünün vektörleştirilmesi hatalı yanıtlara yol açabilir ve otomatik vektör hale getirici kendine bu tür veri bağımlılıklarının olmadığını kanıtlayamıyor.|
|1201|Dizi temeli döngü sırasında değişiyor.|
|1202|Bir yapı birimindeki alan 32 veya 64 bit uzunluğunda değil.|
|1203|Döngü gövdesi, bir diziye bitişik olmayan erişimler içeriyor.|

```cpp
void fn();
void code_1200(int *A)
{
    // Code 1200 is emitted when data dependence is prohibiting
    // vectorization. This can only be resolved by rewriting the
    // loop, and considering the marking of loop function calls as
    // __forceinline.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i-1] + 1; // vectorization-prohibiting
        fn();               // vectorization-prohibiting
    }
}

void code_1201(int *A)
{
    // Code 1201 is emitted when an array base changes
    // in the loop body. Resolve this by rewriting your
    // code so that varying the array base is not necessary.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
        A++;
    }
}

struct S_1202
{
    short a;
    short b;
} s[1000];

short sA[1000], sB[1000], sC[1000];

void code_1202(S_1202 *s)
{
    // Code 1202 is emitted when non-vectorizable struct accesses
    // are present in the loop body. Only struct accesses
    // that are 32 or 64 bits are vectorized.

    for (int i=0; i<1000; ++i)
    {
        s[i].a = s[i].b + 1; // this 16 bit struct access is not vectorizable
        sA[i] += sB[i] * sC[i]; // this ensures we don't emit reason code '1300'
    }
}

void code_1203(int *A)
{
    // Code 1203 is emitted when non-vectorizable memory references
    // are present in the loop body. Vectorization of some non-contiguous
    // memory access is supported - for example, the gather/scatter pattern.

    for (int i=0; i<1000; ++i)
    {
        A[i] += A[0] + 1;       // constant memory access not vectorized
        A[i] += A[i*2+2] + 2;  // non-contiguous memory access not vectorized
    }
}

```

###  <a name="BKMK_ReasonCode130x"></a> 13xx

13*xx* neden kodları otomatik vektör hale getirici için geçerlidir.

|Neden Kodu|Açıklama|
|-----------------|-----------------|
|1300|Döngü gövdesinde hesaplama yok ya da çok az.|
|1301|Döngü adımı + 1 değil.|
|1302|Döngü bir "-sırasında".|
|1303|Vektörleştirmenin değer sağlaması için yeterli sayıda döngü yinelemesi yok.|
|1304|Döngü farklı boyutlarda atamalar içeriyor.|
|1305|Yeterli tür bilgisi yok.|

```cpp
void code_1300(int *A, int *B)
{
    // Code 1300 is emitted when the compiler detects that there is
    // no computation in the loop body.

    for (int i=0; i<1000; ++i)
    {
        A[i] = B[i]; // Do not vectorize, instead emit memcpy
    }
}

void code_1301(int *A)
{
    // Code 1301 is emitted when the stride of a loop is not positive 1.
    // Only loops that have a stride of positive 1 are vectorized;
    // rewriting your loop may be required.

    for (int i=0; i<1000; i += 2)
    {
        A[i] = A[i] + 1;
    }
}

void code_1302(int *A)
{
    // Code 1302 is emitted for "do-while" loops. Only "while"
    // and "for" loops are vectorized.

    int i = 0;
    do
    {
        A[i] = A[i] + 1;
    } while (++i < 1000);
}

int code_1303(int *A, int *B)
{
    // Code 1303 is emitted when the compiler detects that
    // the number of iterations of the loop is too small to
    // make vectorization profitable.

    // If the loop computation fits perfectly in
    // vector registers - for example, the upperbound is 4, or 8 in
    // this case - then the loop _may_ be vectorized.

    // This loop is not vectorized because there are 5 iterations

    for (int i=0; i<5; ++i)
    {
        A[i] = A[i] + 1;
    }

    // This loop is vectorized

    for (int i=0; i<4; ++i)
    {
        A[i] = A[i] + 1;
    }

    // This loop is not vectorized because runtime pointer checks
    // are required to check that A and B don't overlap. It is not
    // worth it to vectorize this loop.

    for (int i=0; i<4; ++i)
    {
        A[i] = B[i] + 1;
    }

    // This loop is not vectorized because of the scalar reduction.

    int s = 0;
    for (int i=0; i<4; ++i)
    {
        s += A[i];
    }
    return s;
}

void code_1304(int *A, short *B)
{
    // Code 1304 is emitted when the compiler detects
    // different sized statements in the loop body.
    // In this case, there is an 32-bit statement and a
    // 16-bit statement.

    // In cases like this consider splitting the loop into loops to
    // maximize vector register utilization.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
        B[i] = B[i] + 1;
    }
}

typedef struct S_1305
{
    int a;
    int b;
} S_1305;

void code_1305( S_1305 *s, S_1305 x)
{
    // Code 1305 is emitted when the compiler can't discern
    // proper vectorizable type information for this loop.
    // This includes non-scalar loop types such as struct
    // assignments, as in this example.

    // Resolve this by ensuring that your loops have statements
    // that operate on integers or floating point types.

    for (int i=0; i<1000; ++i)
    {
        s[i] = x;
    }
}

```

###  <a name="BKMK_ReasonCode140x"></a> 14xx

14*xx* neden kodları otomatik vektörleştirme ile uyumlu olmayan bazı seçeneği belirtildiğinde oluşur.

|Neden Kodu|Açıklama|
|-----------------|-----------------|
|1400|**#pragma loop(no_vector)** belirtilir.|
|1401|**/ Kernel** x86 veya ARM hedeflenirken anahtarı belirtiliyor.|
|1402|**/ arch: SSE2** veya üstü anahtar x86 hedeflenirken belirtilmedi.|
|1403|**çiftlerde** anahtarı belirtiliyor ve döngü işlemler içeriyor.|
|1404|**/ O1** veya **/Os** anahtarı belirtiliyor.|
|1405|Vektörleştirme; dinamik oluşturucudan statik oluşturucuya iyileştirmeye yardımcı olmak üzere devre dışı bırakılır.|

```cpp
void code_1400(int *A)
{
    // Code 1400 is emitted when the no_vector pragma
    // is specified.

#pragma loop(no_vector)
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

// Compile with /kernel
void code_1401(int *A)
{
    // Code 1401 is emitted when /kernel is specified.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

// Compile with /arch:IA32
void code_1402(int *A)
{
    // Code 1401 is emitted when /arch:IA32 is specified.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

// Compile with /favor:ATOM
void code_1403(double *A)
{
    // Code 1401 is emitted when /favor:ATOM is specified, and
    // the loop contains operations on "double" arrays.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

// Compile with /O1 or /Os
void code_1404(int *A)
{
    // Code 1401 is emitted when compiling for size.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

```

###  <a name="BKMK_ReasonCode150x"></a> 15xx

15 bloğunu*xx* neden kodları yumuşatma için geçerlidir. Bellekte bir konuma iki farklı ad tarafından erişilebildiğinde yumuşatma meydana gelir.

|Neden Kodu|Açıklama|
|-----------------|-----------------|
|1500|Çok boyutlu diziler üzerinde olası yumuşatma.|
|1501|Yapı birimlerinin dizilerinde olası yumuşatma.|
|1502|Olası yumuşatma ve dizi dizini n + K öğesinden farklı.|
|1503|Olası yumuşatma ve dizi dizini birden fazla ofset içeriyor.|
|1504|Olası yumuşatma; çok fazla çalışma zamanı denetimi gerektirir.|
|1505|Olası yumuşatma, ancak çalışma zamanı denetimleri çok karmaşık.|

```cpp
void code_1500(int A[100][100], int B[100][100])
{
    // Code 1500 is emitted when runtime pointer
    // disambiguation checks are required, and
    // there are multidimensional array references.

    for (int i=0; i<100; ++i)
    {
        for (int j=0; j<100; ++j)
        {
            A[i][j] = B[i][j] + 1;
        }
    }
}

typedef struct S_1501
{
    int a;
    int b;
} S_1501;

int iA[1000], iB[1000], iC[1000];

void code_1501(S_1501 *s1, S_1501 *s2)
{
    // Code 1501 is emitted when runtime pointer
    // disambiguation checks are required, and
    // there are array-of-struct accesses in the
    // loop body.

    for (int i=0; i<100; ++i)
    {
        s1[i].a = s2[i].b + 1;
        iA[i] += iB[i] * iC[i]; // this is to ensure we don't emit reason code '1300'
    }
}

void code_1502(int *A, int *B)
{
    // Code 1502 is emitted when runtime pointer
    // disambiguation checks are required, and
    // an array reference has an offset that varies
    // in the loop.

    int x = 0;
    for (int i=0; i<100; ++i)
    {
        A[i] = B[i + x] + 1;
        ++x;                   // 'x' varies in the loop
    }
}

void code_1503(int *A, int *B, int x, int y)
{
    // Code 1503 is emitted when runtime pointer
    // disambiguation checks are required, and
    // an array reference has multiple offsets.

    for (int i=0; i<100; ++i)
    {
        A[i] = B[i+x] + B[i+y] + 1;   // multiple offsets when addressing 'B': {x, y}
        A[i] = B[i+x] + B[i] + 1;     // multiple offsets when addressing 'B': {x, 0}
        A[i] = B[i+x] + B[i+x] + 1;   // this is vectorized
    }
}

void code_1504(int *A1, int *A2, int *A3, int *A4,
               int *A5, int *A6, int *A7, int *A8,
               int *A9, int *A10, int *A11, int *A12,
               int *A13, int *A14, int *A15, int *A16)
{
    // Code 1504 is emitted when too many runtime
    // pointer disambiguation checks are required.

    for (int i=0; i<100; ++i)
    {
        ++A1[i];
        ++A2[i];
        ++A3[i];
        ++A4[i];
        ++A5[i];
        ++A6[i];
        ++A7[i];
        ++A8[i];
        ++A9[i];
        ++A10[i];
        ++A11[i];
        ++A12[i];
        ++A13[i];
        ++A14[i];
        ++A15[i];
        ++A16[i];
    }
}

void code_1505(int *A, int *B)
{
    // Code 1505 is emitted when runtime pointer
    // disambiguation checks are required, but are
    // too complex for the compiler to discern.

    for (int i=0; i<100; ++i)
    {
        for (int j=0; j<100; ++j)
        {
            for (int k=0; k<100; ++k)
            {
                A[i+j-k] = B[i-j+k] * 2;
            }
        }
    }
}

```

## <a name="see-also"></a>Ayrıca Bkz.

[Otomatik Paralelleştirme ve Otomatik Vektörleştirme](../../parallel/auto-parallelization-and-auto-vectorization.md)<br/>
[Yerel kodda paralel programlama](http://go.microsoft.com/fwlink/p/?linkid=263662)<br/>
[#pragma loop()](../../preprocessor/loop.md)<br/>
[/Q Seçenekler (Düşük Düzey İşlemler)](../../build/reference/q-options-low-level-operations.md)<br/>
[/Qpar-report (Otomatik Paralel Hale Getirici Raporlama Düzeyi)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)<br/>
[/Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)