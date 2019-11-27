---
title: 'Nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: b0356cfb-12cc-4ee8-b988-8311ed1ab5e0
ms.openlocfilehash: e376eab75b9b1fb4a7a271d05fe037142f22e139
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246536"
---
# <a name="how-to-create-and-use-ccomptr-and-ccomqiptr-instances"></a>Nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma

Klasik Windows programlamada, kitaplıklar genellikle COM nesneleri olarak (veya daha kesin olarak COM sunucuları olarak) uygulanır. Birçok Windows işletim sistemi bileşeni COM sunucusu olarak uygulanır ve birçok katkıda bulunanlar bu biçimde kitaplıklar sağlar. COM temel bilgileri hakkında daha fazla bilgi için bkz. [bileşen nesne modeli (com)](/windows/win32/com/component-object-model--com--portal).

Bileşen nesne modeli (COM) nesnesini örneklediğinizde, arabirim işaretçisini bir COM akıllı İşaretçisinde depolayın ve bu, `AddRef` ve yıkıcıdaki `Release` yapılan çağrıları kullanarak başvuru sayımı gerçekleştirir. Etkin Şablon kitaplığı (ATL) veya Microsoft Foundation Class Kitaplığı (MFC) kullanıyorsanız, `CComPtr` akıllı işaretçiyi kullanın. ATL veya MFC kullanmıyorsanız `_com_ptr_t`kullanın. `std::unique_ptr`COM eşdeğeri olmadığından, bu akıllı işaretçileri hem tek sahip hem de birden çok sahip senaryolar için kullanın. Hem `CComPtr` hem de `ComQIPtr` Rvalue başvuruları olan taşıma işlemlerini destekler.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CComPtr` kullanarak bir COM nesnesi örneğini oluşturma ve arabirimlerine işaretçiler alma işlemlerinin nasıl yapılacağını gösterir. `CComPtr::CoCreateInstance` member işlevinin, aynı ada sahip Win32 işlevi yerine COM nesnesini oluşturmak için kullanıldığını unutmayın.

[!code-cpp[COM_smart_pointers#01](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_1.cpp)]

`CComPtr` ve akrabaları ATL 'nin bir parçasıdır ve \<atlcomclı. h > içinde tanımlanmıştır. `_com_ptr_t`, \<comıp. h > içinde bildirilmiştir. Derleyici, tür kitaplıkları için sarmalayıcı sınıflar oluşturduğunda `_com_ptr_t` özelleştirilmiş bir şekilde oluşturur.

## <a name="example"></a>Örnek

ATL Ayrıca bir COM nesnesini ek bir arabirim almak üzere sorgulamak için daha basit bir sözdizimi olan `CComQIPtr`de sağlar. Ancak, `CComQIPtr` yapabileceği her şeyi `CComPtr` ve ham COM arabirim işaretçileriyle anlam açısından daha tutarlı olduğundan, önerilir. Bir arabirimi sorgulamak için bir `CComPtr` kullanıyorsanız, yeni arabirim işaretçisi bir out parametresine yerleştirilir. Çağrı başarısız olursa, tipik bir COM deseninin olduğu bir HRESULT döndürülür. `CComQIPtr`, dönüş değeri işaretçinin kendisidir ve çağrı başarısız olursa, iç HRESULT dönüş değerine erişilemez. Aşağıdaki iki satır `CComPtr` ve `CComQIPtr` içindeki hata işleme mekanizmalarının nasıl farklı olduğunu gösterir.

[!code-cpp[COM_smart_pointers#02](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_2.cpp)]

## <a name="example"></a>Örnek

`CComPtr`, IDispatch 'in COM Otomasyon bileşenlerine işaretçiler depolamasına ve geç bağlamayı kullanarak arabirimdeki yöntemleri çağırmasına olanak tanıyan bir özelleştirme sağlar. `CComDispatchDriver`, `CComPtr<IDispatch>`örtük olarak dönüştürülebilir `CComQIPtr<IDispatch, &IIDIDispatch>`için bir typedef 'dir. Bu nedenle, bu üç adlardan herhangi biri kodda göründüğünde `CComPtr<IDispatch>`eşdeğerdir. Aşağıdaki örnek, `CComPtr<IDispatch>`kullanarak Microsoft Word nesne modeli için bir işaretçinin nasıl alınacağını gösterir.

[!code-cpp[COM_smart_pointers#03](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)
