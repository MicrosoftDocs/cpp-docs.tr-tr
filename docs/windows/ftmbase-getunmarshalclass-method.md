---
title: FtmBase::GetUnmarshalClass metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs:
- C++
helpviewer_keywords:
- GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c76c2d75f3d8c2e872b29d9ecf07841c99027713
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599509"
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass Metodu

COM kodu için karşılık gelen proxy içeren DLL bulmak için kullandığı CLSID değerini alır. COM proxy'si başlatılmamış bir örneğini oluşturmak için bu DLL'yi yükler.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>Parametreler

*riid*  
Sıralanması arabirimi tanımlayıcısını başvuru.

*BD*  
Sıralanması arabirim işaretçisi; çağıranın istendiği arayüz işaretçisi yoksa NULL olabilir.

*dwDestContext*  
Belirtilen arabirim iptal edilecek olduğu hedef bağlamı.

Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.

Unmarshaling ya da geçerli işlemin (MSHCTX_INPROC) başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlemde ortaya çıkabilir.

*pvDestContext*  
Gelecekte kullanılmak üzere ayrılmış; NULL olmalıdır.

*mshlflags*  
Bu işlem tamamlandığında CLSID istemci işlemini bir ara sunucu oluşturmak için kullanılacak işaretçi.

*Pcıd*

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, S_FALSE.

## <a name="requirements"></a>Gereksinimler

**Başlık:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[FtmBase Sınıfı](../windows/ftmbase-class.md)