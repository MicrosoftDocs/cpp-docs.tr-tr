---
title: "Lambda'lar, işlev nesneleri ve kısıtlanmış işlevler kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: afec84ba6e3c007e576c37b4a7afc71fe62691ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>Lambda'lar, İşlev Nesneleri ve Kısıtlanmış İşlevler Kullanma
Hızlandırıcı üzerinde çalıştırmak istediğiniz C++ AMP kodu bir bağımsız değişken için bir çağrı olarak belirtilen [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) yöntemi. Bu bağımsız değişken olarak bir lambda ifadesi veya bir işlev nesnesi (functor) sağlayabilir. Ayrıca, lambda ifadesi veya işlev nesnesi C++ AMP kısıtlanmış işlevi çağırabilirsiniz. Bu konu, Lambda'lar, işlev nesneleri ve kısıtlanmış işlevler göstermek için bir dizi ek algoritma kullanır. Aşağıdaki örnek, C++ AMP kodu olmadan algoritmasını gösterir. İki 1 boyutlu diziler eşit uzunlukta oluşturulur. Karşılık gelen tamsayı öğeleri eklendi ve üçüncü 1 boyutlu bir dizi içinde depolanır. C++ AMP kullanılmaz.  
  
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
 Kodu yeniden C++ AMP kullanılacak en doğrudan yolu bir lambda ifadesi kullanmaktır.  
  
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
  
 Lambda ifadesi bir dizin oluşturma parametre içermelidir ve içermelidir `restrict(amp)`. Örnekte, [array_view](../../parallel/amp/reference/array-view-class.md) `sum` nesnesi 1 derecesini sahiptir. Bu nedenle, lambda ifadesi parametresidir bir [dizin](../../parallel/amp/reference/index-class.md) , derece 1 sahip bir nesne. Çalışma zamanında lambda ifadesi bir kez her öğe için çalıştırılmasını [array_view](../../parallel/amp/reference/array-view-class.md) nesnesi. Daha fazla bilgi için bkz: [Lambda ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md).  
  
## <a name="function-object"></a>İşlev Nesnesi  
 Hızlandırıcı kod işlevi nesnesine öğeli.  
  
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

 İşlev nesnesi bir oluşturucu içermelidir ve işlev çağırma işleci aşırı içermelidir. İşlev çağırma işleci bir dizin oluşturma parametre içermelidir. İşlev nesnesi örneği ikinci bağımsız değişken olarak geçirilen [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) yöntemi. Bu örnekte, üç [array_view](../../parallel/amp/reference/array-view-class.md) nesneleri işlevi nesne oluşturucuya geçirilir. [Array_view](../../parallel/amp/reference/array-view-class.md) nesne `sum` 1 derecesini sahiptir. Bu nedenle, işlev çağırma işleci parametresidir bir [dizin](../../parallel/amp/reference/index-class.md) , derece 1 sahip bir nesne. Çalışma zamanında işlevi kez her öğe için yürütülür [array_view](../../parallel/amp/reference/array-view-class.md) nesnesi. Daha fazla bilgi için bkz: [işlevini çağırın](../../cpp/function-call-cpp.md) ve [işlev nesneleri C++ Standart Kitaplığı'nda](../../standard-library/function-objects-in-the-stl.md).  
  
## <a name="c-amp-restricted-function"></a>C++ AMP kısıtlanmış işlevi  
 Daha fazla kısıtlı işlevi oluşturarak ve lambda ifadesi veya bir işlev nesnesi çağırma Hızlandırıcı kod öğeli. Aşağıdaki kod örneği, bir lambda ifadesinden kısıtlı bir işlevi çağırmak gösterilmiştir.  
  
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
  
 Sınırlı işlev içermelidir `restrict(amp)` ve açıklanan kısıtlamaları uygun [(C++ AMP) kısıtlamak](../../cpp/restrict-cpp-amp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ AMP (C++ hızlandırılmış yoğun paralellik)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Lambda ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md)   
 [İşlev çağrısı](../../cpp/function-call-cpp.md)   
 [C++ Standart Kitaplığı'nda işlev nesneleri](../../standard-library/function-objects-in-the-stl.md)   
 [restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)

