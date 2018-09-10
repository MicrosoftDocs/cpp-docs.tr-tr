---
title: Platform::IDisposable arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
dev_langs:
- C++
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c596e4054729855ea3c8caedf632ca8dd50b796a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105074"
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable arabirimi

Yönetilmeyen kaynakları serbest bırakmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
public interface class IDisposable
```

## <a name="attributes"></a>Öznitelikler

**GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")

**VersionAttribute**(NTDDI_WIN8)

### <a name="members"></a>Üyeler

IDisposable arayüzünü IUnknown arabirimden devralır. IDisposable ayrıca aşağıdaki türde üyeleri vardır:

**Yöntemler**

IDisposable arayüzünü aşağıdaki yöntemleri içerir.

|Yöntem|Açıklama|
|------------|-----------------|
|Dispose|Yönetilmeyen kaynakları serbest bırakmak için kullanılır.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu