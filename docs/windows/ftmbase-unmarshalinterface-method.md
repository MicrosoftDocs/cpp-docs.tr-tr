---
title: Ftmbase::unmarshalınterface metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ef462ae884aad4160ffbae1883485ac7e06d3aa5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610707"
---
# <a name="ftmbaseunmarshalinterface-method"></a>FtmBase::UnmarshalInterface Metodu

Yeni oluşturulan proxy başlatır ve proxy için bir arabirim işaretçisini döndürür.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*  
Arabirim işaretçisi iptal edilecek olduğu akışa yönelik işaretçi.

*riid*  
İptal edilecek arabirimi tanımlayıcısını başvuru.

*ppv*  
Bu işlem tamamlandığında, istenen arabirim işaretçisi alır bir işaretçi değişkeninin adresini *riid*. Bu işlem başarılı olursa **ppv* iptal edilecek arabiriminin istenen arabirim işaretçisi içerir.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde e_noınterface veya E_FAIL.

## <a name="requirements"></a>Gereksinimler

**Başlık:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[FtmBase Sınıfı](../windows/ftmbase-class.md)