---
title: RESULT_CODE enum
description: C++ Build Insights SDK RESULT_CODE başvuru.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RESULT_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 62874e176c3f3e8f9df1ca64e7b593b7a0ef5c01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323629"
---
# <a name="result_code-enum"></a>RESULT_CODE enum

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Enum `RESULT_CODE` başarı ve başarısızlık koşullarını açıklar.

## <a name="members"></a>Üyeler

| Adı | Değer | Açıklama |
|--|--|--|
| `RESULT_CODE_SUCCESS` | 0 (0x0000000) | İşlem başarılı oldu. |
| `RESULT_CODE_FAILURE_ANALYSIS_ERROR` | 1 (0x00000001) | [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR'daki](relog-descriptor-struct.md) geri arama `CALLBACK_CODE_ANALYSIS_FAILURE` işlevlerinizden biri değeri döndürür. Bu değer [CALLBACK_CODE](callback-code-enum.md) enum üyesidir. |
| `RESULT_CODE_FAILURE_CANCELLED` | 2 (0x00000002) | [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR'daki](relog-descriptor-struct.md) geri arama `CALLBACK_CODE_ANALYSIS_CANCEL` işlevlerinizden biri değeri döndürür. Bu değer [CALLBACK_CODE](callback-code-enum.md) enum üyesidir. |
| `RESULT_CODE_FAILURE_INVALID_INPUT_LOG_FILE` | 3 (0x00000003) | Windows için giriş Olay İzleme (ETW) izleme belirtilen geçersizdir. |
| `RESULT_CODE_FAILURE_INVALID_OUTPUT_LOG_FILE` | 4 (0x00000004) | Belirtilen çıkış ETW izleme geçersizdir. |
| `RESULT_CODE_FAILURE_MISSING_ANALYSIS_CALLBACK` | 5 (0x00000005) | ANALYSIS_CALLBACKS [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) yapısı doğru olarak başharflere alınmadı. |
| `RESULT_CODE_FAILURE_MISSING_RELOG_CALLBACK` | 6 (0x00000006) | [RELOG_CALLBACKS](relog-callbacks-struct.md) yapısı doğru olarak başharfe getirilmemiş. |
| `RESULT_CODE_FAILURE_OPEN_INPUT_TRACE` | 7 (0x00000007) | Giriş ETW izlemesini açamadı. |
| `RESULT_CODE_FAILURE_PROCESS_TRACE` | 8 (0x00000008) | Giriş ETW izleme işlerken bir hata oluştu. |
| `RESULT_CODE_FAILURE_START_RELOGGER` | 9 (0x00000009) | Yeniden günlüğe kaydetme oturumunu başlatmaya çalışırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_DROPPED_EVENTS` | 10 (0x0000000A) | Giriş ETW izleme önemli olaylar eksik. |
| `RESULT_CODE_FAILURE_UNSUPPORTED_OS` | 11 (0x000000B) | Windows'un desteklenmeyen bir sürümünde C++ Build Insights kullanıyorsunuz. |
| `RESULT_CODE_FAILURE_INVALID_TRACING_SESSION_NAME` | 12 (0x0000000C) | Sağlanan oturum adı geçersizdir. |
| `RESULT_CODE_FAILURE_INSUFFICIENT_PRIVILEGES` | 13 (0x000000D) | Bu işlem yönetici ayrıcalıkları gerektirir. |
| `RESULT_CODE_FAILURE_GENERATE_GUID` | 14 (0x000000E) | GUID oluştururken bir hata oluştu. |
| `RESULT_CODE_FAILURE_OBTAINING_TEMP_DIRECTORY` | 15 (0x000000F) | Geçici dizin yolunu belirlemeye çalışırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_CREATE_TEMPORARY_DIRECTORY` | 16 (0x0000010) | Başlatılan izleme oturumu için geçici bir dizin oluşturmaya çalışırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_START_SYSTEM_TRACE` | 17 (0x0000011) | Sistem izlemeyi başlatmaya çalışırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_START_MSVC_TRACE` | 18 (0x00000012) | MSVC izleme sini başlatmaya çalışırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_STOP_MSVC_TRACE` | 19 (0x00000013) | MSVC izlemesini durdurmaya çalışırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_STOP_SYSTEM_TRACE` | 20 (0x00000014) | Sistem izlemeyi başlatmaya çalışırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_SESSION_DIRECTORY_RESOLUTION` | 21 (0x00000015) | İzleme durduruldu, ancak izleme oturumunun geçici dizini bulunamıyor. |
| `RESULT_CODE_FAILURE_MSVC_TRACE_FILE_NOT_FOUND` | 22 (0x00000016) | Durdurulan MSVC izleme dosyası bulunamıyor. |
| `RESULT_CODE_FAILURE_MERGE_TRACES` | 23 (0x00000017) | Çekirdek İzleme Denetimi kullanarak izlemeleri birleştirirken bir hata oluştu. |
| `RESULT_CODE_FAILURE_UNKNOWN_ERROR` | 24 (0x00000018) | Bilinmeyen bir hata oluştu. |

::: moniker-end
