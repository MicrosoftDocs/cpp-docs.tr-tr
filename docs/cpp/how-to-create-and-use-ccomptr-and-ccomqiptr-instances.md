---
title: 'Nasıl yapılır: Oluşturma ve CComPtr ve CComQIPtr örnekleri kullanma'
ms.custom: how-to
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b0356cfb-12cc-4ee8-b988-8311ed1ab5e0
ms.openlocfilehash: 2bcabfe80185939b899c84fc44f71b98608fc3c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154067"
---
# <a name="how-to-create-and-use-ccomptr-and-ccomqiptr-instances"></a>Nasıl yapılır: Oluşturma ve CComPtr ve CComQIPtr örnekleri kullanma

Klasik Windows programlamada kitaplıkları genellikle COM nesneleri (veya daha kesin olarak COM sunucuları) uygulanır. Çoğu Windows işletim sistemi bileşenleri COM sunucuları olarak uygulanır ve bu formda kitaplıkları, çok sayıda katkıda sağlar. COM temelleri hakkında daha fazla bilgi için bkz. [Bileşen Nesne Modeli (COM)](/windows/desktop/com/component-object-model--com--portal).

Bir Bileşen Nesne Modeli (COM) nesnenin örneğini oluştururken, arabirim işaretçisi çağrıları kullanarak başvuru sayımı gerçekleştirir bir COM akıllı işaretçi depolar `AddRef` ve `Release` yok edici içinde. Etkin Şablon kitaplığı (ATL) veya Microsoft Foundation Class Kitaplığı'nı (MFC) kullanıyorsanız, ardından kullanmak `CComPtr` akıllı işaretçi. ATL veya MFC kullanmıyorsanız kullanın, ardından `_com_ptr_t`. Eşdeğer hiçbir COM olduğundan `std::unique_ptr`, hem tek sahibi hem de birden çok sahip senaryolar için bu akıllı işaretçileri kullanın. Her ikisi de `CComPtr` ve `ComQIPtr` destek rvalue başvuruları olan işlemler taşıyın.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `CComPtr` bir COM nesnesi ve arabirimlerinden işaretçileri edinmek için. Dikkat `CComPtr::CoCreateInstance` üye işlevi aynı ada sahip bir Win32 işlevini yerine bir COM nesnesi oluşturmak için kullanılır.

[!code-cpp[COM_smart_pointers#01](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_1.cpp)]

`CComPtr` kendi Akraba ATL parçası olan ve tanımlanan \<atlcomcli.h >. `_com_ptr_t` bölümünde bildirilen \<comip.h >. Derleyici uzmanlıkları oluşturur `_com_ptr_t` ürettiği tür kitaplığı Sarmalayıcı sınıfların zaman.

## <a name="example"></a>Örnek

ATL ayrıca sağlar `CComQIPtr`, ek bir arabirimi almak için bir COM nesnesi sorgulamak için basit bir sözdizimi vardır. Öneririz ancak `CComPtr` bunu her şeyi yapar çünkü `CComQIPtr` anlamsal olarak ham COM arabirim işaretçilerini ile daha tutarlı ve bunu yapabilirsiniz. Kullanıyorsanız bir `CComPtr` sorgulamak için bir arabirimi için yeni bir arabirim işaretçisi out parametresi yerleştirilir. Çağrı başarısız olursa, tipik bir COM Düzen olduğu HRESULT döndürülür. İle `CComQIPtr`işaretçi dönüş değeridir ve çağrı başarısız olursa, iç HRESULT dönüş değerini erişilemez. Aşağıdaki iki satırları göster nasıl hata işleme mekanizması içinde `CComPtr` ve `CComQIPtr` farklılık gösterir.

[!code-cpp[COM_smart_pointers#02](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_2.cpp)]

## <a name="example"></a>Örnek

`CComPtr` bir özelleştirmesi sağlayan COM Otomasyon bileşenleri işaretçileri depolayın ve geç bağlama kullanarak arabirimindeki yöntemleri çağırmak için IDispatch sağlar. `CComDispatchDriver` için bir TypeDef `CComQIPtr<IDispatch, &IIDIDispatch>`, örtük olarak dönüştürülebilir olduğu `CComPtr<IDispatch>`. Bu üç ad hiçbirini kodda göründüğünde, bu nedenle, eşdeğerdir `CComPtr<IDispatch>`. Aşağıdaki örneği kullanarak Microsoft Word nesne modelinde bir işaretçi alma işlemi gösterilmektedir bir `CComPtr<IDispatch>`.

[!code-cpp[COM_smart_pointers#03](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)
