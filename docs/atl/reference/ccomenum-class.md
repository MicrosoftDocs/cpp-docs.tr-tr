---
title: CComEnum sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f9dff61a62eec37a503b1c0018ead6dce33065a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077119"
---
# <a name="ccomenum-class"></a>CComEnum sınıfı

Bu sınıf, bir dizi üzerinde temel bir COM Numaralandırıcı nesnesi tanımlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
T,
    Copy>,
public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>Parametreler

*temel*<br/>
COM Numaralandırıcı arabirimi. Bkz: [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) örneği.

*piid*<br/>
Numaralandırıcı arabirimi arabirim kimliği için bir işaretçi.

*T*<br/>
Numaralandırıcı arabirim tarafından sunulan öğe türü.

*kopyalama*<br/>
Bir homojen [kopyalama İlkesi sınıfı](../../atl/atl-copy-policy-classes.md).

*ThreadModel*<br/>
Sınıfın iş parçacığı modeli. Bu parametre, projenizde kullanılan genel nesnesi iş parçacığı modelini varsayılan kullanır.

## <a name="remarks"></a>Açıklamalar

`CComEnum` bir dizi üzerinde temel bir COM Numaralandırıcı nesnesi tanımlar. Bu sınıf için benzer [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) bir C++ Standart Kitaplığı kapsayıcı dayalı bir numaralandırıcı uygular. Bu sınıf kullanmak için tipik adımları aşağıda özetlenmiştir. Daha fazla bilgi için [ATL koleksiyonları ve numaralandırıcıları](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class"></a>Bu sınıf kullanmak için:

- **TypeDef** bu sınıfın özelleştirmesi.

- Kullanım **typedef** özelleştirmesi şablon bağımsız değişken olarak `CComObject`.

- Bir örneğini oluşturmak `CComObject` özelleştirmesi.

- Numaralandırıcı nesnesi çağırarak denetlediği başlatmak [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).

- Numaralandırıcı arabirimi istemciye döndürür.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)

`CComEnum`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="example"></a>Örnek

Aşağıda gösterilen kod oluşturma ve bir numaralandırıcı nesnesi başlatılırken yeniden kullanılabilir bir işlev sağlar.

[!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]

Bu şablon işlevi uygulamak için kullanılan `_NewEnum` aşağıda gösterildiği gibi bir toplama arabirimin özelliği:

[!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]

Bu kod oluşturur bir **typedef** için `CComEnum` çeşitler arasında oluşan bir vektörü sunan `IEnumVariant` arabirimi. `CVariantArrayCollection` Sınıfı yalnızca uzmanlaşmış `CreateEnumerator` bu türde ve geçişleri gerekli bağımsız değişkenler Numaralandırıcı nesnelerle çalışmayı.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[CComEnumImpl Sınıfı](../../atl/reference/ccomenumimpl-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)
