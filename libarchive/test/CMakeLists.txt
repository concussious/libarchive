############################################
#
# How to build libarchive_test
#
############################################
IF(ENABLE_TEST)
  SET(libarchive_test_SOURCES
    ../../test_utils/test_utils.c
    ../../test_utils/test_main.c
    read_open_memory.c
    test.h
    test_7zip_filename_encoding.c
    test_acl_nfs4.c
    test_acl_pax.c
    test_acl_platform_nfs4.c
    test_acl_platform_posix1e.c
    test_acl_posix1e.c
    test_acl_text.c
    test_ar_mode.c
    test_archive_api_feature.c
    test_archive_clear_error.c
    test_archive_cmdline.c
    test_archive_digest.c
    test_archive_match_owner.c
    test_archive_match_path.c
    test_archive_match_time.c
    test_archive_parse_date.c
    test_archive_pathmatch.c
    test_archive_read.c
    test_archive_read_add_passphrase.c
    test_archive_read_close_twice.c
    test_archive_read_close_twice_open_fd.c
    test_archive_read_close_twice_open_filename.c
    test_archive_read_multiple_data_objects.c
    test_archive_read_next_header_empty.c
    test_archive_read_next_header_raw.c
    test_archive_read_open2.c
    test_archive_read_set_filter_option.c
    test_archive_read_set_format_option.c
    test_archive_read_set_option.c
    test_archive_read_set_options.c
    test_archive_read_support.c
    test_archive_set_error.c
    test_archive_string.c
    test_archive_string_conversion.c
    test_archive_write_add_filter_by_name.c
    test_archive_write_set_filter_option.c
    test_archive_write_set_format_by_name.c
    test_archive_write_set_format_filter_by_ext.c
    test_archive_write_set_format_option.c
    test_archive_write_set_option.c
    test_archive_write_set_options.c
    test_archive_write_set_passphrase.c
    test_bad_fd.c
    test_compat_bzip2.c
    test_compat_cpio.c
    test_compat_gtar.c
    test_compat_gtar_large.c
    test_compat_gzip.c
    test_compat_lz4.c
    test_compat_lzip.c
    test_compat_lzma.c
    test_compat_lzop.c
    test_compat_mac.c
    test_compat_perl_archive_tar.c
    test_compat_plexus_archiver_tar.c
    test_compat_solaris_pax_sparse.c
    test_compat_solaris_tar_acl.c
    test_compat_star_acl.c
    test_compat_tar_directory.c
    test_compat_tar_hardlink.c
    test_compat_uudecode.c
    test_compat_uudecode_large.c
    test_compat_xz.c
    test_compat_zip.c
    test_compat_zstd.c
    test_empty_write.c
    test_entry.c
    test_entry_strmode.c
    test_extattr_freebsd.c
    test_filter_count.c
    test_fuzz.c
    test_gnutar_filename_encoding.c
    test_link_resolver.c
    test_open_failure.c
    test_open_fd.c
    test_open_file.c
    test_open_filename.c
    test_pax_filename_encoding.c
    test_pax_xattr_header.c
    test_read_data_large.c
    test_read_disk.c
    test_read_disk_directory_traversals.c
    test_read_disk_entry_from_file.c
    test_read_extract.c
    test_read_file_nonexistent.c
    test_read_filter_compress.c
    test_read_filter_grzip.c
    test_read_filter_gzip_recursive.c
    test_read_filter_lrzip.c
    test_read_filter_lzop.c
    test_read_filter_lzop_multiple_parts.c
    test_read_filter_program.c
    test_read_filter_program_signature.c
    test_read_filter_uudecode.c
    test_read_filter_uudecode_raw.c
    test_read_format_7zip.c
    test_read_format_7zip_encryption_data.c
    test_read_format_7zip_encryption_header.c
    test_read_format_7zip_encryption_partially.c
    test_read_format_7zip_malformed.c
    test_read_format_7zip_packinfo_digests.c
    test_read_format_ar.c
    test_read_format_cab.c
    test_read_format_cab_filename.c
    test_read_format_cpio_afio.c
    test_read_format_cpio_bin.c
    test_read_format_cpio_bin_Z.c
    test_read_format_cpio_bin_be.c
    test_read_format_cpio_bin_bz2.c
    test_read_format_cpio_bin_gz.c
    test_read_format_cpio_bin_le.c
    test_read_format_cpio_bin_lzip.c
    test_read_format_cpio_bin_lzma.c
    test_read_format_cpio_bin_xz.c
    test_read_format_cpio_filename.c
    test_read_format_cpio_odc.c
    test_read_format_cpio_svr4_bzip2_rpm.c
    test_read_format_cpio_svr4_gzip.c
    test_read_format_cpio_svr4_gzip_rpm.c
    test_read_format_cpio_svr4c_Z.c
    test_read_format_empty.c
    test_read_format_gtar_filename.c
    test_read_format_gtar_gz.c
    test_read_format_gtar_lzma.c
    test_read_format_gtar_redundant_L.c
    test_read_format_gtar_sparse.c
    test_read_format_gtar_sparse_length.c
    test_read_format_gtar_sparse_skip_entry.c
    test_read_format_huge_rpm.c
    test_read_format_iso_Z.c
    test_read_format_iso_multi_extent.c
    test_read_format_iso_xorriso.c
    test_read_format_isojoliet_bz2.c
    test_read_format_isojoliet_long.c
    test_read_format_isojoliet_rr.c
    test_read_format_isojoliet_versioned.c
    test_read_format_isorr_bz2.c
    test_read_format_isorr_ce.c
    test_read_format_isorr_new_bz2.c
    test_read_format_isorr_rr_moved.c
    test_read_format_isozisofs_bz2.c
    test_read_format_lha.c
    test_read_format_lha_bugfix_0.c
    test_read_format_lha_filename.c
    test_read_format_lha_filename_utf16.c
    test_read_format_mtree.c
    test_read_format_mtree_crash747.c
    test_read_format_pax_bz2.c
    test_read_format_rar.c
    test_read_format_rar_encryption.c
    test_read_format_rar_encryption_data.c
    test_read_format_rar_encryption_header.c
    test_read_format_rar_encryption_partially.c
    test_read_format_rar_invalid1.c
    test_read_format_rar_filter.c
    test_read_format_rar_overflow.c
    test_read_format_rar5.c
    test_read_format_raw.c
    test_read_format_tar.c
    test_read_format_tar_concatenated.c
    test_read_format_tar_empty_filename.c
    test_read_format_tar_empty_with_gnulabel.c
    test_read_format_tar_empty_pax.c
    test_read_format_tar_filename.c
    test_read_format_tar_invalid_pax_size.c
    test_read_format_tar_mac_metadata.c
    test_read_format_tar_pax_g_large.c
    test_read_format_tar_pax_large_attr.c
    test_read_format_tbz.c
    test_read_format_tgz.c
    test_read_format_tlz.c
    test_read_format_txz.c
    test_read_format_tz.c
    test_read_format_ustar_filename.c
    test_read_format_warc.c
    test_read_format_xar.c
    test_read_format_xar_doublelink.c
    test_read_format_zip.c
    test_read_format_zip_7075_utf8_paths.c
    test_read_format_zip_comment_stored.c
    test_read_format_zip_encryption_data.c
    test_read_format_zip_encryption_header.c
    test_read_format_zip_encryption_partially.c
    test_read_format_zip_extra_padding.c
    test_read_format_zip_filename.c
    test_read_format_zip_high_compression.c
    test_read_format_zip_jar.c
    test_read_format_zip_mac_metadata.c
    test_read_format_zip_malformed.c
    test_read_format_zip_msdos.c
    test_read_format_zip_nested.c
    test_read_format_zip_nofiletype.c
    test_read_format_zip_padded.c
    test_read_format_zip_sfx.c
    test_read_format_zip_traditional_encryption_data.c
    test_read_format_zip_winzip_aes.c
    test_read_format_zip_winzip_aes_large.c
    test_read_format_zip_zip64.c
    test_read_format_zip_with_invalid_traditional_eocd.c
    test_read_large.c
    test_read_pax_empty_val_no_nl.c
    test_read_pax_xattr_rht_security_selinux.c
    test_read_pax_xattr_schily.c
    test_read_pax_truncated.c
    test_read_position.c
    test_read_set_format.c
    test_read_too_many_filters.c
    test_read_truncated.c
    test_read_truncated_filter.c
    test_short_writes.c
    test_sparse_basic.c
    test_tar_filenames.c
    test_tar_large.c
    test_ustar_filename_encoding.c
    test_ustar_filenames.c
    test_warn_missing_hardlink_target.c
    test_write_disk.c
    test_write_disk_appledouble.c
    test_write_disk_failures.c
    test_write_disk_fixup.c
    test_write_disk_hardlink.c
    test_write_disk_hfs_compression.c
    test_write_disk_lookup.c
    test_write_disk_mac_metadata.c
    test_write_disk_no_hfs_compression.c
    test_write_disk_perms.c
    test_write_disk_secure.c
    test_write_disk_secure_noabsolutepaths.c
    test_write_disk_secure744.c
    test_write_disk_secure745.c
    test_write_disk_secure746.c
    test_write_disk_sparse.c
    test_write_disk_symlink.c
    test_write_disk_times.c
    test_write_filter_b64encode.c
    test_write_filter_bzip2.c
    test_write_filter_compress.c
    test_write_filter_gzip.c
    test_write_filter_gzip_timestamp.c
    test_write_filter_lrzip.c
    test_write_filter_lz4.c
    test_write_filter_lzip.c
    test_write_filter_lzma.c
    test_write_filter_lzop.c
    test_write_filter_program.c
    test_write_filter_uuencode.c
    test_write_filter_xz.c
    test_write_filter_zstd.c
    test_write_format_7zip.c
    test_write_format_7zip_empty.c
    test_write_format_7zip_large.c
    test_write_format_ar.c
    test_write_format_cpio.c
    test_write_format_cpio_empty.c
    test_write_format_cpio_newc.c
    test_write_format_cpio_odc.c
    test_write_format_gnutar.c
    test_write_format_gnutar_filenames.c
    test_write_format_iso9660.c
    test_write_format_iso9660_boot.c
    test_write_format_iso9660_empty.c
    test_write_format_iso9660_filename.c
    test_write_format_iso9660_zisofs.c
    test_write_format_mtree.c
    test_write_format_mtree_absolute_path.c
    test_write_format_mtree_classic.c
    test_write_format_mtree_classic_indent.c
    test_write_format_mtree_fflags.c
    test_write_format_mtree_no_separator.c
    test_write_format_mtree_preset_digests.c
    test_write_format_mtree_quoted_filename.c
    test_write_format_pax.c
    test_write_format_raw.c
    test_write_format_raw_b64.c
    test_write_format_shar_empty.c
    test_write_format_tar.c
    test_write_format_tar_empty.c
    test_write_format_tar_sparse.c
    test_write_format_tar_ustar.c
    test_write_format_tar_v7tar.c
    test_write_format_warc.c
    test_write_format_warc_empty.c
    test_write_format_xar.c
    test_write_format_xar_empty.c
    test_write_format_zip.c
    test_write_format_zip64_stream.c
    test_write_format_zip_compression_store.c
    test_write_format_zip_compression_bzip2.c
    test_write_format_zip_compression_lzmaxz.c
    test_write_format_zip_compression_zstd.c
    test_write_format_zip_empty.c
    test_write_format_zip_empty_zip64.c
    test_write_format_zip_entry_size_unset.c
    test_write_format_zip_file.c
    test_write_format_zip_file_zip64.c
    test_write_format_zip_large.c
    test_write_format_zip_stream.c
    test_write_format_zip_windows_path.c
    test_write_format_zip_zip64.c
    test_write_open_memory.c
    test_write_read_format_zip.c
    test_xattr_platform.c
    test_zip_filename_encoding.c
  )

  #
  # Register target
  #
  ADD_EXECUTABLE(libarchive_test ${libarchive_test_SOURCES})
  TARGET_LINK_LIBRARIES(libarchive_test archive_static ${ADDITIONAL_LIBS})
  SET_PROPERTY(TARGET libarchive_test PROPERTY COMPILE_DEFINITIONS
    LIBARCHIVE_STATIC LIST_H)

  #
  # Generate list.h by grepping DEFINE_TEST() lines out of the C sources.
  #
  GENERATE_LIST_H(${CMAKE_CURRENT_BINARY_DIR}/list.h
    ${CMAKE_CURRENT_LIST_FILE} ${libarchive_test_SOURCES})
  SET_PROPERTY(DIRECTORY APPEND PROPERTY INCLUDE_DIRECTORIES
    ${CMAKE_CURRENT_BINARY_DIR})

  # list.h has a line DEFINE_TEST(testname) for every
  # test.  We can use that to define the tests for cmake by
  # defining a DEFINE_TEST macro and reading list.h in.
  MACRO (DEFINE_TEST _testname)
    ADD_TEST(
      NAME libarchive_${_testname}
      COMMAND libarchive_test -vv
                              -r ${CMAKE_CURRENT_SOURCE_DIR}
                              -s
                              ${_testname})
    SET_TESTS_PROPERTIES(libarchive_${_testname} PROPERTIES SKIP_RETURN_CODE 2)
  ENDMACRO (DEFINE_TEST _testname)

  INCLUDE(${CMAKE_CURRENT_BINARY_DIR}/list.h)
  INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR})
  INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/test_utils)
  INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/libarchive/test)

  # Experimental new test handling
  ADD_CUSTOM_TARGET(run_libarchive_test
	COMMAND	libarchive_test -r ${CMAKE_CURRENT_SOURCE_DIR} -vv)
  ADD_DEPENDENCIES(run_all_tests run_libarchive_test)
ENDIF(ENABLE_TEST)

