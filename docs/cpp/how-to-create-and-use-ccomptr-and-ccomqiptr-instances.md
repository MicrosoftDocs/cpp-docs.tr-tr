---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma'
title: 'Nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: b0356cfb-12cc-4ee8-b988-8311ed1ab5e0
ms.openlocfilehash: c16d908e3df9e10641f1264aed7623463424de69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268658"
---
# <a name="how-to-create-and-use-ccomptr-and-ccomqiptr-instances"></a>Nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma

Klasik Windows programlamada, kitaplıklar genellikle COM nesneleri olarak (veya daha kesin olarak COM sunucuları olarak) uygulanır. Birçok Windows işletim sistemi bileşeni COM sunucusu olarak uygulanır ve birçok katkıda bulunanlar bu biçimde kitaplıklar sağlar. COM temel bilgileri hakkında daha fazla bilgi için bkz. [bileşen nesne modeli (com)](/windows/win32/com/component-object-model--com--portal).

Bir bileşen nesne modeli (COM) nesnesi örneğini başlattığınızda, arabirim işaretçisini, `AddRef` `Release` yok edicinin ve yıkıcısında yapılan çağrıları kullanarak bir com akıllı İşaretçisinde depolayın. Etkin Şablon kitaplığı (ATL) veya Microsoft Foundation Class Kitaplığı (MFC) kullanıyorsanız `CComPtr` akıllı işaretçiyi kullanın. ATL veya MFC kullanmıyorsanız, öğesini kullanın `_com_ptr_t` . İçin COM eşdeğeri olmadığından `std::unique_ptr` , bu akıllı işaretçileri hem tek sahip hem de birden çok sahip senaryolar için kullanın. Hem hem de `CComPtr` `ComQIPtr` Rvalue başvuruları olan taşıma işlemlerini destekler.

## <a name="example-ccomptr"></a>Örnek: CComPtr

Aşağıdaki örnek, `CComPtr` BIR COM nesnesinin örneğini oluşturmak ve arabirimlerine işaretçiler almak için kullanımını gösterir. `CComPtr::CoCreateInstance`Üye işlevinin, aynı ada sahip Win32 işlevi yerıne com nesnesini oluşturmak için kullanıldığını unutmayın.

[!code-cpp[COM_smart_pointers#01](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_1.cpp)]

`CComPtr` ve bunun akrabaları ATL 'nin bir parçasıdır ve ' de tanımlanmıştır \<atlcomcli.h> . `_com_ptr_t` içinde bildirilmiştir \<comip.h> . Derleyici, `_com_ptr_t` tür kitaplıkları için sarmalayıcı sınıflar oluşturduğunda uzmanlık özelliklerini oluşturur.

## <a name="example-ccomqipt"></a>Örnek: CComQIPt

ATL Ayrıca `CComQIPtr` BIR com nesnesini ek bir arabirim almak üzere sorgulamak için daha basit bir sözdizimine sahiptir. Ancak, bunu yapabileceği `CComPtr` her şeyi yaptığından, `CComQIPtr` ham com arabirim işaretçileriyle anlam açısından daha tutarlı olması önerilir. Bir `CComPtr` arabirim için bir sorgu kullanırsanız, yeni arabirim işaretçisi bir out parametresine yerleştirilir. Çağrı başarısız olursa, tipik bir COM deseninin olduğu bir HRESULT döndürülür. İle `CComQIPtr` , dönüş değeri işaretçinin kendisidir ve çağrı başarısız olursa, Iç HRESULT dönüş değerine erişilemez. Aşağıdaki iki satır, ' deki ve farklı hata işleme mekanizmalarının nasıl `CComPtr` `CComQIPtr` farklılık gösterir.

[!code-cpp[COM_smart_pointers#02](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_2.cpp)]

## <a name="example-idispatch"></a>Örnek: IDispatch

`CComPtr` IDispatch 'in COM Otomasyon bileşenlerine işaretçiler depolamasını ve geç bağlamayı kullanarak arabirimdeki yöntemleri çağırmasını sağlayan bir IDispatch özelleştirmesi sağlar. `CComDispatchDriver` , için örtük olarak `CComQIPtr<IDispatch, &IIDIDispatch>` dönüştürülebilir olan için bir typedef `CComPtr<IDispatch>` . Bu nedenle, bu üç adlardan herhangi biri kodda göründüğünde, öğesine eşdeğerdir `CComPtr<IDispatch>` . Aşağıdaki örnek, kullanarak Microsoft Word nesne modeli için bir işaretçinin nasıl alınacağını gösterir `CComPtr<IDispatch>` .

[!code-cpp[COM_smart_pointers#03](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)
