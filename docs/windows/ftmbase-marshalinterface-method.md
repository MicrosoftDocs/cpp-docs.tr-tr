---
title: Ftmbase::marshalınterface metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a95521123a87a6ae68ce9f923779c1a6ceda4ccf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599717"
---
# <a name="ftmbasemarshalinterface-method"></a>FtmBase::MarshalInterface Metodu

Bir akışa bir proxy nesnesi içinde bazı istemci işlemini başlatmak için gerekli verileri yazar.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHODIMP MarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*  
Hazırlama sırasında kullanılmak üzere stream işaretçisi.

*riid*  
Sıralanması arabirimi tanımlayıcısını başvuru. Bu arabirim nesnesinden türetilmesi `IUnknown` arabirimi.

*BD*  
İşaretçi sıralanması arabirim işaretçisi için; çağıranın istendiği arayüz işaretçisi yoksa NULL olabilir.

*dwDestContext*  
Belirtilen arabirim iptal edilecek olduğu hedef bağlamı.

Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.

Unmarshaling, geçerli işlemin (MSHCTX_INPROC) başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlemde ortaya çıkabilir.

*pvDestContext*  
Gelecekte kullanılmak üzere ayrılmış; sıfır olmalıdır.

*mshlflags*  
İstemci işlemine aktarılacak veri sıralanması olup olmadığını belirtir: genellikle bu durum — burada da alınabilir birden çok istemci tarafından genel bir tablo yazılamaz veya okunamaz.

## <a name="return-value"></a>Dönüş Değeri

Arabirim işaretçisi S_OK başarılı bir şekilde sıralanır.

Belirtilen arabirim e_noınterface desteklenmiyor.

Akış STG_E_MEDIUMFULL dolu.

E_FAIL işlemi başarısız oldu.

## <a name="requirements"></a>Gereksinimler

**Başlık:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[FtmBase Sınıfı](../windows/ftmbase-class.md)