---
title: 'Nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b0356cfb-12cc-4ee8-b988-8311ed1ab5e0
ms.openlocfilehash: 8dd7aa903eefd533b1dd2688f3cee46ab3787e60
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498587"
---
# <a name="how-to-create-and-use-ccomptr-and-ccomqiptr-instances"></a>Nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma

Klasik Windows programlamada, kitaplıklar genellikle COM nesneleri olarak (veya daha kesin olarak COM sunucuları olarak) uygulanır. Birçok Windows işletim sistemi bileşeni COM sunucusu olarak uygulanır ve birçok katkıda bulunanlar bu biçimde kitaplıklar sağlar. COM temel bilgileri hakkında daha fazla bilgi için bkz. [bileşen nesne modeli (com)](/windows/win32/com/component-object-model--com--portal).

Bir bileşen nesne modeli (com) nesnesi örneğini başlattığınızda, arabirim işaretçisini, yok edicinin `AddRef` ve `Release` yıkıcısında yapılan çağrıları kullanarak bir com akıllı İşaretçisinde depolayın. Etkin Şablon kitaplığı (ATL) veya Microsoft Foundation Class Kitaplığı (MFC) kullanıyorsanız `CComPtr` akıllı işaretçiyi kullanın. ATL veya MFC kullanmıyorsanız, öğesini kullanın `_com_ptr_t`. İçin `std::unique_ptr`com eşdeğeri olmadığından, bu akıllı işaretçileri hem tek sahip hem de birden çok sahip senaryolar için kullanın. Hem hem de `CComPtr` Rvalue başvuruları olan taşıma işlemlerini destekler.`ComQIPtr`

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir com nesnesinin örneğini `CComPtr` oluşturmak ve arabirimlerine işaretçiler almak için kullanımını gösterir. `CComPtr::CoCreateInstance` Üye işlevinin, aynı ada sahip Win32 işlevi yerine com nesnesini oluşturmak için kullanıldığını unutmayın.

[!code-cpp[COM_smart_pointers#01](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_1.cpp)]

`CComPtr`ve onun akrabaları ATL 'nin bir parçasıdır ve atlcomclı. h > içinde \<tanımlanmıştır. `_com_ptr_t`comıp. \<h > içinde bildirilmiştir. Derleyici, tür kitaplıkları için sarmalayıcı `_com_ptr_t` sınıflar oluşturduğunda uzmanlık özelliklerini oluşturur.

## <a name="example"></a>Örnek

ATL ayrıca `CComQIPtr`bir com nesnesini ek bir arabirim almak üzere sorgulamak için daha basit bir sözdizimine sahiptir. Ancak, bunu yapabileceği `CComPtr` `CComQIPtr` her şeyi yaptığından, ham com arabirim işaretçileriyle anlam açısından daha tutarlı olması önerilir. Bir arabirim için bir `CComPtr` sorgu kullanırsanız, yeni arabirim işaretçisi bir out parametresine yerleştirilir. Çağrı başarısız olursa, tipik bir COM deseninin olduğu bir HRESULT döndürülür. İle `CComQIPtr`, dönüş değeri işaretçinin kendisidir ve çağrı başarısız olursa, iç HRESULT dönüş değerine erişilemez. Aşağıdaki iki satır, ' deki `CComPtr` ve `CComQIPtr` farklı hata işleme mekanizmalarının nasıl farklılık gösterir.

[!code-cpp[COM_smart_pointers#02](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_2.cpp)]

## <a name="example"></a>Örnek

`CComPtr`IDispatch 'in COM Otomasyon bileşenlerine işaretçiler depolamasını ve geç bağlamayı kullanarak arabirimdeki yöntemleri çağırmasını sağlayan bir IDispatch özelleştirmesi sağlar. `CComDispatchDriver`, için örtük olarak `CComQIPtr<IDispatch, &IIDIDispatch>` `CComPtr<IDispatch>`dönüştürülebilir olan için bir typedef. Bu nedenle, bu üç adlardan herhangi biri kodda göründüğünde, öğesine `CComPtr<IDispatch>`eşdeğerdir. Aşağıdaki örnek, kullanarak Microsoft Word nesne modeli için bir `CComPtr<IDispatch>`işaretçinin nasıl alınacağını gösterir.

[!code-cpp[COM_smart_pointers#03](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)
