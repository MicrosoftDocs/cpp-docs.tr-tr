---
title: Module::RegisterCOMObject yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterCOMObject method
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abbe93f5359171c88134ff61759e9edc63db2451
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610439"
---
# <a name="moduleregistercomobject-method"></a>Module::RegisterCOMObject Yöntemi

Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla COM nesneleri kaydeder.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);

```

### <a name="parameters"></a>Parametreler

*SunucuAdı*  
Bir sunucunun tam adı.

*CLSID*  
CLSID kaydetmek için bir dizi.

*fabrikaları*  
IUnknown arabirimi olan kullanılabilirlik yayımlanan sınıf nesnelerinin dizisi.

*Tanımlama bilgileri*  
İşlem tamamlandığında, kayıtlı olan bir sınıfı değerleri için işaretçiler dizisi nesneleri. Bu değerler daha sonra kullanılır kaydını iptal etme.

*Sayısı*  
Kaydedilecek CLSID sayısı.

## <a name="return-value"></a>Dönüş Değeri

S_OK varsa saldırgan; Aksi takdirde, bir HRESULT nedenini belirten CO_E_OBJISREG gibi işlem başarısız oldu.

## <a name="remarks"></a>Açıklamalar

COM nesnelerinin CLSCTX numaralandırma CLSCTX_LOCAL_SERVER Numaralandırıcı ile kaydedilir.

Kayıtlı nesneler için bağlantı türü, geçerli bir birleşimi tarafından belirtilen *comflag* şablon parametresi ile REGCLS numaralandırma REGCLS_SUSPENDED Numaralandırıcı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
[Modül Sınıfı](../windows/module-class.md)