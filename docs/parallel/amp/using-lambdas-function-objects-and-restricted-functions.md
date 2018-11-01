---
title: Lambda'lar, İşlev Nesneleri ve Kısıtlanmış İşlevler Kullanma
ms.date: 11/04/2016
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
ms.openlocfilehash: 819605eac6408751456479fbc3daa38aac1418ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629404"
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>Lambda'lar, İşlev Nesneleri ve Kısıtlanmış İşlevler Kullanma

Hızlandırıcı da çalıştırmayı istediğiniz C++ AMP kodunu çağrısında bağımsız değişken olarak belirtilen [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) yöntemi. Bu bağımsız değişken olarak bir lambda ifadesi veya işlev nesnesi (functor) sağlayabilir. Ayrıca, lambda ifadesi veya işlev nesnesi bir C++ AMP-kısıtlı işlevi çağırabilir. Bu konu, lambdaları, işlev nesneleri ve kısıtlı işlevleri göstermek için bir dizi toplama algoritması kullanır. Aşağıdaki örnek, C++ AMP kodu olmayan algoritmayı gösterir. Eşit uzunluktaki iki 1 boyutlu dizi oluşturulur. Karşılık tamsayı öğeleri eklenir ve üçüncü 1 boyutlu dizide depolanan. C++ AMP kullanılmaz.

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

## <a name="lambda-expression"></a>Lambda ifadesi

Bir lambda ifadesini kullanma, C++ AMP kodunu yeniden yazmak için kullanılacak en direkt yoldur.

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

Lambda ifadesi bir dizin parametresi ve içermelidir `restrict(amp)`. Örnekte, [array_view](../../parallel/amp/reference/array-view-class.md) `sum` nesnesinin derecesi 1 vardır. Bu nedenle lambda ifadesi parametresi olan bir [dizin](../../parallel/amp/reference/index-class.md) 1. dereceli bir nesne. Çalışma zamanında, lambda ifadesi bir defa her öğe için yürütülür [array_view](../../parallel/amp/reference/array-view-class.md) nesne. Daha fazla bilgi için [Lambda ifadesi söz dizimi](../../cpp/lambda-expression-syntax.md).

## <a name="function-object"></a>İşlev Nesnesi

Hızlandırıcı kodunu işlen bir işlev nesnesine ayırabilirsiniz.

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

İşlev nesnesi bir oluşturucu ve bir işlev çağrısı işleci aşırı yüklemesi içermelidir. İşlev çağrısı işleci, bir dizin oluşturma parametresi de içermelidir. İkinci bağımsız değişkeni olarak geçirilen işlev nesnesinin bir örneği [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) yöntemi. Bu örnekte, üç [array_view](../../parallel/amp/reference/array-view-class.md) nesne işlev nesnesi oluşturucusuna geçirilmektedir geçirilir. [Array_view](../../parallel/amp/reference/array-view-class.md) nesne `sum` derecesi 1 sahiptir. Bu nedenle, işlev çağrısı işleci parametresi olan bir [dizin](../../parallel/amp/reference/index-class.md) 1. dereceli bir nesne. Çalışma zamanında işlev bir defa her öğe için yürütülür [array_view](../../parallel/amp/reference/array-view-class.md) nesne. Daha fazla bilgi için [işlevi çağrısı](../../cpp/function-call-cpp.md) ve [C++ Standart kitaplığındaki işlev nesneleri](../../standard-library/function-objects-in-the-stl.md).

## <a name="c-amp-restricted-function"></a>C++ AMP-kısıtlı işlevi

Sınırlı bir işlev oluşturarak ve bir lambda ifadesi veya işlev nesnesi çağırarak Hızlandırıcı kodunu daha da ayırabilirsiniz. Aşağıdaki kod örneği, bir lambda ifadesinden sınırlı bir işlev çağrısı gösterilmiştir.

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

Sınırlı işlev içermelidir `restrict(amp)` ve şurada açıklanan kısıtlamalarına uymak [(C++ AMP) kısıtlama](../../cpp/restrict-cpp-amp.md).

## <a name="see-also"></a>Ayrıca Bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Lambda İfadesi Söz Dizimi](../../cpp/lambda-expression-syntax.md)<br/>
[İşlev Çağrısı](../../cpp/function-call-cpp.md)<br/>
[C++ Standart Kitaplığındaki İşlev Nesneleri](../../standard-library/function-objects-in-the-stl.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)