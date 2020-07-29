---
title: CComEnumOnSTL sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
ms.openlocfilehash: b0674d64b471318d972d209373e0d74af0fa77f5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226600"
---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL sınıfı

Bu sınıf, bir C++ standart kitaplığı koleksiyonunu temel alan bir COM Numaralandırıcı nesnesi tanımlar.

## <a name="syntax"></a>Söz dizimi

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

*Temel*<br/>
COM numaralandırıcısı. Örnek için bkz. [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*piıd*<br/>
Numaralandırıcı arabiriminin arabirim KIMLIĞINE yönelik bir işaretçi.

*T*<br/>
Numaralandırıcı arabirimi tarafından kullanıma sunulan öğenin türü.

*Kopyala*<br/>
Bir [kopyalama ilkesi](../../atl/atl-copy-policy-classes.md) sınıfı.

*CollType*<br/>
C++ standart kitaplığı kapsayıcı sınıfı.

## <a name="remarks"></a>Açıklamalar

`CComEnumOnSTL`C++ standart kitaplığı koleksiyonunu temel alan bir COM Numaralandırıcı nesnesi tanımlar. Bu sınıf, kendi içinde veya [ıollectiononstlımpl](../../atl/reference/icollectiononstlimpl-class.md)ile birlikte kullanılabilir. Bu sınıfı kullanmanın tipik adımları aşağıda özetlenmiştir. Daha fazla bilgi için bkz. [atl koleksiyonları ve Numaralandırıcılar](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Bu sınıfı ıollectiononstlımpl ile kullanmak için:

- **`typedef`** Bu sınıfın özelleştirmesi.

- **`typedef`** Özelleştirme içinde son şablon bağımsız değişkeni olarak ' i kullanın `ICollectionOnSTLImpl` .

Bir örnek için bkz. [atl koleksiyonları ve Numaralandırıcılar](../../atl/atl-collections-and-enumerators.md) .

## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Bu sınıfı ıollectiononstlımpl 'dan bağımsız olarak kullanmak için:

- **`typedef`** Bu sınıfın özelleştirmesi.

- **`typedef`** Bir özelleştirmesi içinde şablon bağımsız değişkeni olarak kullanın `CComObject` .

- Özelleşmenin bir örneğini oluşturun `CComObject` .

- [IEnumOnSTLImpl:: Init](../../atl/reference/ienumonstlimpl-class.md#init)çağırarak Numaralandırıcı nesnesini başlatın.

- Numaralandırıcı arabirimini istemciye döndürün.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)

`CComEnumOnSTL`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="example"></a>Örnek

Aşağıda gösterilen kod, bir Numaralandırıcı nesnesinin oluşturulmasını ve başlatılmasını işlemek için genel bir işlev sağlar:

[!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]

Bu şablon işlevi, `_NewEnum` aşağıda gösterildiği gibi bir koleksiyon arabiriminin özelliğini uygulamak için kullanılabilir:

[!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]

Bu kod **`typedef`** `CComEnumOnSTL` , arabirimi aracılığıyla bir vektör vektörü sunan için bir oluşturur `CComVariant` `IEnumVariant` . `CVariantCollection`Sınıfı, `CreateSTLEnumerator` Bu türün Numaralandırıcı nesneleriyle birlikte çalışmak için de uzmanlaşmış.

## <a name="see-also"></a>Ayrıca bkz.

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)<br/>
[ATLCollections örneği: ıollectiononstlımpl, CComEnumOnSTL ve özel kopyalama Ilkesi sınıflarını gösterir](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[IEnumOnSTLImpl sınıfı](../../atl/reference/ienumonstlimpl-class.md)
