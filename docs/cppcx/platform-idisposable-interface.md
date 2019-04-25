---
title: Platform::IDisposable arabirimi
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
ms.openlocfilehash: f114959321c0ed3879a089b944a5ff1b19843118
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257835"
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

**En düşük desteklenen istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** Platform