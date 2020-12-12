---
description: 'Hakkında daha fazla bilgi edinin: Lambdalar, Işlev nesneleri ve kısıtlanmış Işlevler kullanma'
title: Lambda'lar, İşlev Nesneleri ve Kısıtlanmış İşlevler Kullanma
ms.date: 11/04/2016
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
ms.openlocfilehash: bef02f30b5d5b5f11b8051c7a596ac0a141eef0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314457"
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>Lambda'lar, İşlev Nesneleri ve Kısıtlanmış İşlevler Kullanma

Hızlandırıcıda çalıştırmak istediğiniz C++ AMP kodu, [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) yöntemine yapılan çağrıda bir bağımsız değişken olarak belirtilir. Bu bağımsız değişken olarak bir lambda ifadesi ya da bir işlev nesnesi (functor) sağlayabilirsiniz. Ayrıca, lambda ifadesi veya işlev nesnesi C++ AMP kısıtlı bir işlevi çağırabilir. Bu konuda Lambdalar, işlev nesneleri ve kısıtlanmış işlevleri göstermek için dizi ekleme algoritması kullanılmaktadır. Aşağıdaki örnek, C++ AMP kodu olmadan algoritmayı gösterir. 2 1-eşit uzunluktaki boyut dizileri oluşturulur. Karşılık gelen tamsayı öğeleri üçüncü bir 1 boyutlu diziye eklenir ve saklanır. C++ AMP kullanılmıyor.

```cpp
void CpuMethod() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    for (int idx = 0; idx <5; idx++)
    {
        sumCPP[idx] = aCPP[idx] + bCPP[idx];
    }

    for (int idx = 0; idx <5; idx++)
    {
        std::cout <<sumCPP[idx] <<"\n";
    }
}
```

## <a name="lambda-expression"></a>Lambda Ifadesi

Lambda ifadesinin kullanılması, kodu yeniden yazmak için C++ AMP kullanmanın en doğrudan yoludur.

```cpp
void AddArraysWithLambda() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
             sum[idx] = a[idx] + b[idx];
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Lambda ifadesi bir dizin oluşturma parametresi içermeli ve içermelidir `restrict(amp)` . Örnekte, [array_view](../../parallel/amp/reference/array-view-class.md) `sum` nesnesinin derecesi 1 ' dir. Bu nedenle, lambda ifadesine yönelik parametre, 1. sıra olan bir [Dizin](../../parallel/amp/reference/index-class.md) nesnesidir. Çalışma zamanında, [array_view](../../parallel/amp/reference/array-view-class.md) nesnesindeki her öğe için lambda ifadesi bir kez yürütülür. Daha fazla bilgi için bkz. [lambda Ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md).

## <a name="function-object"></a>İşlev Nesnesi

Hızlandırıcı kodunu bir işlev nesnesi olarak çarpanlara atayabilirsiniz.

```cpp
class AdditionFunctionObject
{
public:
    AdditionFunctionObject(const array_view<int, 1>& a,
    const array_view<int, 1>& b,
    const array_view<int, 1>& sum)
    : a(a), b(b), sum(sum)
    {
    }

    void operator()(index<1> idx) restrict(amp)
    {
        sum[idx] = a[idx] + b[idx];
    }

private:
    array_view<int, 1> a;
    array_view<int, 1> b;
    array_view<int, 1> sum;
};

void AddArraysWithFunctionObject() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        AdditionFunctionObject(a, b, sum));

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

İşlev nesnesi bir Oluşturucu içermelidir ve işlev çağrısı işlecinin aşırı yüklemesini içermelidir. İşlev çağrısı işleci bir dizin oluşturma parametresi içermelidir. İşlev nesnesinin bir örneği, [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) metoduna ikinci bağımsız değişken olarak geçirilir. Bu örnekte, işlev nesne oluşturucusuna üç [array_view](../../parallel/amp/reference/array-view-class.md) nesne geçirilir. [Array_view](../../parallel/amp/reference/array-view-class.md) nesnesinin `sum` derecesi 1 ' dir. Bu nedenle, işlev çağrısı işlecinin parametresi, sıra 1 olan bir [Dizin](../../parallel/amp/reference/index-class.md) nesnesidir. Çalışma zamanında, işlev [array_view](../../parallel/amp/reference/array-view-class.md) nesnesindeki her öğe için bir kez yürütülür. Daha fazla bilgi için bkz. [C++ standart kitaplığındaki](../../standard-library/function-objects-in-the-stl.md) [Işlev çağrısı](../../cpp/function-call-cpp.md) ve işlev nesneleri.

## <a name="c-amp-restricted-function"></a>C++ AMP-Restricted Işlevi

Bir kısıtlanmış işlev oluşturarak ve bunu bir lambda ifadesinden veya bir işlev nesnesinden çağırarak Hızlandırıcı kodunu daha fazla çarpanda yapabilirsiniz. Aşağıdaki kod örneği bir lambda ifadesinden kısıtlı işlevin nasıl çağrılacağını gösterir.

```cpp
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)
{
    sum[idx] = a[idx] + b[idx];
}

void AddArraysWithFunction() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<int, 1> a(5, aCPP);

    array_view<int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
            AddElementsWithRestrictedFunction(idx, sum, a, b);
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Kısıtlamalı işlev, `restrict(amp)` [restrict (C++ amp)](../../cpp/restrict-cpp-amp.md)bölümünde açıklanan kısıtlamalara uymalıdır ve bunları karşılamalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Lambda Ifadesi söz dizimi](../../cpp/lambda-expression-syntax.md)<br/>
[İşlev çağrısı](../../cpp/function-call-cpp.md)<br/>
[C++ standart kitaplığındaki işlev nesneleri](../../standard-library/function-objects-in-the-stl.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)
