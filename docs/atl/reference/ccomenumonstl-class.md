---
title: CComEnumOnSTL sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
ms.openlocfilehash: 7b1efb3bd574edde59f6d8845d73a51dfabea433
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626622"
---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL sınıfı

Bu sınıf, bir C++ Standart Kitaplığı koleksiyonuna bağlı bir COM Numaralandırıcı nesnesi tanımlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
T,
    Copy,
CollType>,
    public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>Parametreler

*temel*<br/>
Bir COM Numaralandırıcı. Bkz: [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) örneği.

*piid*<br/>
Numaralandırıcı arabirimi arabirim kimliği için bir işaretçi.

*T*<br/>
Numaralandırıcı arabirim tarafından sunulan öğe türü.

*Kopyala*<br/>
A [kopyalama İlkesi](../../atl/atl-copy-policy-classes.md) sınıfı.

*CollType*<br/>
Bir C++ Standart Kitaplığı kapsayıcı sınıfı.

## <a name="remarks"></a>Açıklamalar

`CComEnumOnSTL` bir C++ Standart Kitaplığı koleksiyonuna bağlı bir COM Numaralandırıcı nesnesi tanımlar. Bu sınıf kendi veya o ilkelerle birlikte kullanılabilir [Icollectiononstlımpl](../../atl/reference/icollectiononstlimpl-class.md). Bu sınıf kullanmak için tipik adımları aşağıda özetlenmiştir. Daha fazla bilgi için [ATL koleksiyonları ve numaralandırıcıları](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Bu sınıf Icollectiononstlımpl ile kullanmak için:

- **TypeDef** bu sınıfın özelleştirmesi.

- Kullanım **typedef** özelleştirmesi son şablon bağımsız değişken olarak `ICollectionOnSTLImpl`.

Bkz: [ATL koleksiyonları ve numaralandırıcıları](../../atl/atl-collections-and-enumerators.md) örneği.

## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Bu sınıf Icollectiononstlımpl bağımsız olarak kullanmak için:

- **TypeDef** bu sınıfın özelleştirmesi.

- Kullanım **typedef** özelleştirmesi şablon bağımsız değişken olarak `CComObject`.

- Bir örneğini oluşturmak `CComObject` özelleştirmesi.

- Numaralandırıcı nesnesi çağırarak denetlediği başlatmak [IEnumOnSTLImpl::Init](../../atl/reference/ienumonstlimpl-class.md#init).

- Numaralandırıcı arabirimi istemciye döndürür.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[Ienumonstlımpl](../../atl/reference/ienumonstlimpl-class.md)

`CComEnumOnSTL`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="example"></a>Örnek

Aşağıda gösterilen kod oluşturulması ve başlatılması bir sabit listesi nesnesi işlemek için genel bir işlev sağlar:

[!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]

Bu şablon işlevi uygulamak için kullanılan `_NewEnum` aşağıda gösterildiği gibi bir toplama arabirimin özelliği:

[!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]

Bu kod oluşturur bir **typedef** için `CComEnumOnSTL` oluşan bir vektörü sunan `CComVariant`s yoluyla `IEnumVariant` arabirimi. `CVariantCollection` Sınıfı yalnızca uzmanlaşmış `CreateSTLEnumerator` Numaralandırıcı bu tür nesnelerle çalışmayı.

## <a name="see-also"></a>Ayrıca Bkz.

[Ienumonstlımpl](../../atl/reference/ienumonstlimpl-class.md)<br/>
[ATLCollections örnek: Icollectiononstlımpl ve CComEnumOnSTL özel kopyalama İlkesi sınıfları gösterir](../../visual-cpp-samples.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[IEnumOnSTLImpl Sınıfı](../../atl/reference/ienumonstlimpl-class.md)
