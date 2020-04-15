---
title: eşzamanlı ad alanı sabitleri
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::AgentEventGuid
- concrt/concurrency::COOPERATIVE_TIMEOUT_INFINITE
- concrt/concurrency::COOPERATIVE_WAIT_TIMEOUT
- concrt/concurrency::ConcRTEventGuid
- concrt/concurrency::ConcRT_ProviderGuid
- concrt/concurrency::INHERIT_THREAD_PRIORITY
- concrt/concurrency::LockEventGuid
- concrt/concurrency::PPLParallelForEventGuid
- concrt/concurrency::PPLParallelForeachEventGuid
- concrt/concurrency::ResourceManagerEventGuid
- concrt/concurrency::ScheduleGroupEventGuid
- concrt/concurrency::VirtualProcessorEventGuid
ms.assetid: 6f81fc4c-b10c-479e-8717-9c292360d5a0
ms.openlocfilehash: 8e9254e966f480538d80721bcfd86d301fac8d09
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372729"
---
# <a name="concurrency-namespace-constants"></a>eşzamanlı ad alanı sabitleri

||||
|-|-|-|
|[AgentEventGuid](#agenteventguid)|[CONCRT_RM_VERSION_1](#concrt_rm_version_1)|[COOPERATIVE_TIMEOUT_INFINITE](#cooperative_timeout_infinite)|
|[COOPERATIVE_WAIT_TIMEOUT](#cooperative_wait_timeout)|[ChoreEventGuid](#choreeventguid)|[ConcRTEventGuid](#concrteventguid)|
|[ConcRT_ProviderGuid](#concrt_providerguid)|[BağlamEventGuid](#contexteventguid)|[INHERIT_THREAD_PRIORITY](#inherit_thread_priority)|
|[LockEventGuid](#lockeventguid)|[MaxExecutionResources](#maxexecutionresources)|[PPLParallelForEventGuid](#pplparallelforeventguid)|
|[PPLParallelForeachEventGuid](#pplparallelforeacheventguid)|[PPLParallelInvokeEventGuid](#pplparallelinvokeeventguid)|[Kaynak YöneticisiEventGuid](#resourcemanagereventguid)|
|[ProgramGroupEventGuid](#schedulegroupeventguid)|[SchedulerEventGuid](#schedulereventguid)|[VirtualProcessorEventGuid](#virtualprocessoreventguid)|

## <a name="agenteventguid"></a><a name="agenteventguid"></a>AgentEventGuid

Eşzamanlıçalışma Zamanında Ajanlar kitaplığı tarafından ateşlenen ETW olaylarını açıklayan bir kategori GUID ({B9B5B78C-0713-4898-A21A-C67949DCED07}).

```cpp
const __declspec(selectany) GUID AgentEventGuid = {0xb9b5b78c, 0x713, 0x4898, { 0xa2, 0x1a, 0xc6, 0x79, 0x49, 0xdc, 0xed, 0x7 } };
```

## <a name="choreeventguid"></a><a name="choreeventguid"></a>ChoreEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılan ve angarya işler veya görevlerle doğrudan ilişkili olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID ChoreEventGuid =
    { 0x7E854EC7, 0xCDC4, 0x405a, { 0xB5, 0xB2, 0xAA, 0xF7, 0xC9, 0xE7, 0xD4, 0x0C } };
```

### <a name="remarks"></a>Açıklamalar

Bu kategorideki olaylar şu anda Eşzamanlı Çalışma Zamanı tarafından yürütülmez.

## <a name="concrt_providerguid"></a><a name="concrt_providerguid"></a>ConcRT_ProviderGuid

Eşzamanlılık Çalışma Zamanı için ETW sağlayıcısı GUID.

```cpp
const __declspec(selectany) GUID ConcRT_ProviderGuid =
    { 0xF7B697A3, 0x4DB5, 0x4d3b, { 0xBE, 0x71, 0xC4, 0xD2, 0x84, 0xE6, 0x59, 0x2F } };
```

## <a name="concrt_rm_version_1"></a><a name="concrt_rm_version_1"></a>CONCRT_RM_VERSION_1

Visual Studio 2010'da tanımlanan Kaynak Yöneticisi arabiriminin desteğini gösterir.

```cpp
const unsigned int CONCRT_RM_VERSION_1 = 0x00010000;
```

## <a name="concrteventguid"></a><a name="concrteventguid"></a>ConcRTEventGuid

Eşzamanlı Çalışma Zamanı tarafından ateşlenen ve başka bir kategori tarafından özel olarak tanımlanmamış ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID ConcRTEventGuid =
    { 0x72B14A7D, 0x704C, 0x423e, { 0x92, 0xF8, 0x7E, 0x6D, 0x64, 0xBC, 0xB9, 0x2A } };
```

### <a name="remarks"></a>Açıklamalar

Bu kategorideki olaylar şu anda Eşzamanlı Çalışma Zamanı tarafından yürütülmez.

## <a name="cooperative_timeout_infinite"></a><a name="cooperative_timeout_infinite"></a>COOPERATIVE_TIMEOUT_INFINITE

Beklemenin asla zaman dolmaması gerektiğini belirten değer.

```cpp
const unsigned int COOPERATIVE_TIMEOUT_INFINITE = (unsigned int)-1;
```

## <a name="cooperative_wait_timeout"></a><a name="cooperative_wait_timeout"></a>COOPERATIVE_WAIT_TIMEOUT

Bekleme süresinin dolduğunu belirten değer.

```cpp
const size_t COOPERATIVE_WAIT_TIMEOUT = SIZE_MAX;
```

## <a name="contexteventguid"></a><a name="contexteventguid"></a>BağlamEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve bağlamlarla doğrudan ilişkili Olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID ContextEventGuid =
    { 0x5727A00F, 0x50BE, 0x4519, { 0x82, 0x56, 0xF7, 0x69, 0x98, 0x71, 0xFE, 0xCB } };
```

## <a name="inherit_thread_priority"></a><a name="inherit_thread_priority"></a>INHERIT_THREAD_PRIORITY

Zamanlayıcıdaki tüm `ContextPriority` bağlamların iş parçacığı önceliğinin zamanlayıcıyı oluşturan iş parçacığıyla aynı olması gerektiğini belirten ilke anahtarı için özel değer.

```cpp
const unsigned int INHERIT_THREAD_PRIORITY = 0x0000F000;
```

## <a name="lockeventguid"></a><a name="lockeventguid"></a>LockEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve kilitler ile doğrudan ilişkili Olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID LockEventGuid =
    { 0x79A60DC6, 0x5FC8, 0x4952, { 0xA4, 0x1C, 0x11, 0x63, 0xAE, 0xEC, 0x5E, 0xB8 } };
```

### <a name="remarks"></a>Açıklamalar

Bu kategorideki olaylar şu anda Eşzamanlı Çalışma Zamanı tarafından yürütülmez.

## <a name="maxexecutionresources"></a><a name="maxexecutionresources"></a>MaxExecutionResources

İlke anahtarları `MinConcurrency` için `MaxConcurrency`özel değer ve . Diğer kısıtlamaların yokluğunda makinedeki donanım iş parçacığı sayısı varsayılandır.

```cpp
const unsigned int MaxExecutionResources = 0xFFFFFFFF;
```

## <a name="pplparallelforeventguid"></a><a name="pplparallelforeventguid"></a>PPLParallelForEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve `parallel_for` işlevin kullanımıyla doğrudan ilişkili olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID PPLParallelForEventGuid =
    { 0x31c8da6b, 0x6165, 0x4042, { 0x8b, 0x92, 0x94, 0x9e, 0x31, 0x5f, 0x4d, 0x84 } };
```

## <a name="pplparallelforeacheventguid"></a><a name="pplparallelforeacheventguid"></a>PPLParallelForeachEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve `parallel_for_each` işlevin kullanımıyla doğrudan ilişkili olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID PPLParallelForeachEventGuid =
    { 0x5cb7d785, 0x9d66, 0x465d, { 0xba, 0xe1, 0x46, 0x11, 0x6, 0x1b, 0x54, 0x34 } };
```

## <a name="pplparallelinvokeeventguid"></a><a name="pplparallelinvokeeventguid"></a>PPLParallelInvokeEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve `parallel_invoke` işlevin kullanımıyla doğrudan ilişkili olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID PPLParallelInvokeEventGuid =
    { 0xd1b5b133, 0xec3d, 0x49f4, { 0x98, 0xa3, 0x46, 0x4d, 0x1a, 0x9e, 0x46, 0x82 } };
```

## <a name="resourcemanagereventguid"></a><a name="resourcemanagereventguid"></a>Kaynak YöneticisiEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve kaynak yöneticisiyle doğrudan ilişkili olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID ResourceManagerEventGuid =
    { 0x2718D25B, 0x5BF5, 0x4479, { 0x8E, 0x88, 0xBA, 0xBC, 0x64, 0xBD, 0xBF, 0xCA } };
```

### <a name="remarks"></a>Açıklamalar

Bu kategorideki olaylar şu anda Eşzamanlı Çalışma Zamanı tarafından yürütülmez.

## <a name="schedulegroupeventguid"></a><a name="schedulegroupeventguid"></a>ProgramGroupEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve zamanlama gruplarıyla doğrudan ilişkili Olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID ScheduleGroupEventGuid =
    { 0xE8A3BF1F, 0xA86B, 0x4390, { 0x9C, 0x60, 0x53, 0x90, 0xB9, 0x69, 0xD2, 0x2C } };
```

### <a name="remarks"></a>Açıklamalar

Bu kategorideki olaylar şu anda Eşzamanlı Çalışma Zamanı tarafından yürütülmez.

## <a name="schedulereventguid"></a><a name="schedulereventguid"></a>SchedulerEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve zamanlayıcı etkinliğiyle doğrudan ilişkili olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID SchedulerEventGuid =
    { 0xE2091F8A, 0x1E0A, 0x4731, { 0x84, 0xA2, 0x0D, 0xD5, 0x7C, 0x8A, 0x52, 0x61 } };
```

## <a name="virtualprocessoreventguid"></a><a name="virtualprocessoreventguid"></a>VirtualProcessorEventGuid

Eşzamanlı Çalışma Zamanı tarafından çalıştırılabilen ve sanal işlemcilerle doğrudan ilişkili olan ETW olaylarını açıklayan bir kategori GUID.

```cpp
const __declspec(selectany) GUID VirtualProcessorEventGuid =
    { 0x2f27805f, 0x1676, 0x4ecc, { 0x96, 0xfa, 0x7e, 0xb0, 0x9d, 0x44, 0x30, 0x2f } };
```

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
