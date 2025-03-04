## 5.3.0 (2022-07-20) [Milestone](https://github.com/dropbox/dropbox-sdk-java/milestone/1?closed=1)
---------------------------------------------
- Update dropbox-api-spec to point to more recent version (July 13, 2022) [#400](https://github.com/dropbox/dropbox-sdk-java/pull/400)
- The generateStone Gradle Task now supports Gradle Configuration Caching [#390](https://github.com/dropbox/dropbox-sdk-java/pull/390)
- API Backwards Compatibility Fix - Won't crash when new types are returned from API [#395](https://github.com/dropbox/dropbox-sdk-java/pull/395)
- Version Bumps in the Dropbox Android Sample Apps [#391](https://github.com/dropbox/dropbox-sdk-java/pull/391)

5.2.0 (2022-04-04)
---------------------------------------------
- Update jackson-core to 2.7.9

5.1.1 (2021-12-17)
---------------------------------------------
- Bug fixes for build breakages in 5.1.0

5.1.0 (2021-12-09)
---------------------------------------------
- Upgrade to Gradle 7.2
- Bumped Java source and target compatability to 11

5.0.0 (2021-10-12)
---------------------------------------------
- Upgrade OKHttp to V4
- Mark PipedRequestBody as a one shot request to avoid potential data corrupting during upload
- Expose progress listener for upload progress via getOutputStream, useful for concurrent uploads

4.0.1 (2021-08-26)
---------------------------------------------
- Return an error when we have an invalid access token
- DbxRefreshResult Expires In returns the right time

4.0.0 (2021-03-29)
---------------------------------------------
- update Java tests to use Google's Truth library
- bump target Java version from 6 to 8

3.2.1 (2021-03-29)
---------------------------------------------
- revert Java version bump (back to Java 6)

3.2.0 (2021-03-22)
---------------------------------------------
- update Java tests to use Google's Truth library
- bump target Java version from 6 to 8

3.1.5 (2020-08-11)
---------------------------------------------
- Fix bug in authorization flow.
- Files Namespace
  - Add internal_error to SearchError union.
  - Add locked to LookupError union.
  - Add cant_move_into_vault to RelocationError union.
  - Add MoveIntoVaultError union.
  - Add SearchMatchFieldOptions struct.
  - Add optional match_field_options to SearchV2Arg struct.
  - Doc/example changes.
- Sharing Namespace
  - Add is_vault to SharePathError union.
  - Add invalid_shared_folder to AddFolderMemberError union.
- Team Namespace
  - Make members field of LegalHoldsPolicyUpdateArg struct optional.
  - Add app_folder_removal_not_supported to RevokeLinkedAppError union.
  - Doc/example changes.
- Team Log Namespace
  - Add auto_approve to InviteMethod union.
  - Add moved_from_another_team to InviteMethod union.
  - Add moved_from_another_team to MemberStatus union.
  - Add no_one to SharedLinkVisibility union.
  - Add optional new_team to MemberChangeStatusDetails struct.
  - Add optional previous_team to MemberChangeStatusDetails struct.
  - Add external_sharing_create_report_details to EventDetails union.
  - Add external_sharing_report_failed to EventDetails union.
  - Add content_administration_policy_changed_details to EventDetails
union.
  - Add external_sharing_create_report to EventType union.
  - Add external_sharing_report_failed to EventType union.
  - Add content_administration_policy_changed to EventType union.
  - Add send_for_signature_policy_changed_details to EventDetails union.
  - Add external_sharing_create_report to EventTypeArgs union.
  - Add external_sharing_report_failed to EventTypeArgs union.
  - Add content_administration_policy_changed to EventTypeArgs union.
  - Add send_for_signature_policy_changed to EventTypeArgs union.
  - Add SendForSignaturePolicy union.
  - Add ExternalSharingCreateReportDetails struct.
  - Add ExternalSharingReportFailedDetails struct.
  - Add ContentAdministrationPolicyChangedDetails struct.
  - Add SendForSignaturePolicyChangedDetails struct.
  - Add ExternalSharingCreateReportType struct.
  - Add ExternalSharingReportFailedType struct.
  - Add ContentAdministrationPolicyChangedType struct.
  - Add SendForSignaturePolicyChangedType struct.

3.1.4 (2020-06-08)
---------------------------------------------
- Support include_granted_scopes in OAuth2 flow.
- Support new scope parameter when refreshing DbxCredential.
- Files Namespace:
  - Update comments on FileLockMetadata struct
  - Add optional lockholder_account_id to FileLockMetadata struct
  - Add optional invalid_argument to SearchError union
  - Add get_thumbnail:2 route
  - Add ThumbnailV2Error union
  - Add MinimalFileLinkMetadata struct
  - Add PreviewResult struct
  - Add SharedLinkFileInfo struct
  - Add PathOrLink union
  - Add ThumbnailV2Arg struct
  - Change UnlockFileArg's path type to WritePathOrId
  - Change LockFileArg's path type to WritePathOrId

- Update query description on SearchArg Struct, SearchV2Arg Struct
- Update move:2 and move_batch:2 route descirption

- File Properties Namespace
  - Update AddPropertiesArg description
  - Add duplicate_property_groups to InvalidPropertyGroupError Union
  - Update property_groups description on AddPropertiesError Union

- Shared Links Namespace:
  - Fix Typo

- Team Groups Namespace:
  - Add add_creator_as_owner to GroupCreateArg struct
  - Update comments for async_job_id on GroupMembersChangeResult struct

- Team Legal Holds Namespace:
  - Add exporting to LegalHoldStatus union
  - Add invactive_legal_hold to LegalHoldsListHeldRevisionsError union
  - Add legal_hold_policy_not_found to LegalHoldsPolicyUpdateError union

  - Add MembersInfo struct
  - Add LegalHoldsError union

  - mark legal_holds/export_policy to deprecated
  - mark legal_holds/export_policy_job_status/check to deprecated

  - Change LegalHoldPolicy's members type to MembersInfo
  - Update LegalHoldPolicy's examples
  - Update LegalHoldsPolicyCreateError to extend LegalHoldsError
  - Update LegalHoldsGetPolicyError to extend LegalHoldsError
  - Update LegalHoldsListPoliciesError to extend LegalHoldsError
  - Update LegalHoldsPolicyUpdateError to extend LegalHoldsError
  - Deleted deprecated routes legal_holds/export_policy and legal_holds/export_policy_job_status/check
  - Added comments to legalHoldPolicy struct
  - Add more detailed comments to LegalHoldsListHeldRevisionResult
  - Fix misc typos in comments

- Team_log namespace:
  - Add team_exceeded_legal_hold_quota to LegalHoldsPolicyCreateError union
  - Change LegalHoldsListHeldRevisionsError and LegalHoldsPolicyReleaseError to extend LegalHoldsError
  - Add optional EventTypeArg event_type to GetTeamEventsArg struct
  - Add invalid_filters to GetTeamEventsError union

- Team Log Namespace:
  - Remove lifespan comment

- Team Log Generated Namesapce:
  - Add team_invite_details to ActionDetails union
  - Add optional has_linked_apps to JoinTeamDetails struct
  - Add optional has_linked_devices to JoinTeamDetails struct
  - Add optional has_linkeD_shared_folders to JoinTeamDetails struct
  - Update comments in JoinTeamDetails struct
  - Update JoinTeamDetails struct examples
  - Update LegalHoldsExportAHoldDetails struct examples
  - Update PaperContentRemoveFromFolderDetails target_asset_index to be optional
  - Update PaperContentRemoveFromFolderDetails parent_asset_index to be optional
  - Add shared_content_link to SharedLinkSettingsAddExpirationDetails struct
  - Update SharedLinkSettingAddExpirationDetails struct examples
  - Add optional shared_content_link to SharedLinkSettingsAddPasswordDetails struct
  - Add optional shared_content_link to SharedLinkSettingsAllowDownloadDisabledDetails struct
  - Add optional shared_content_link to SharedLinkSettingsAllowDownloadEnabledDetails struct
  - Add optional shared_content_link to SharedLinkSettingsChangeAudienceDetails struct
  - Add optional shared_content_link to SharedLinkSettingsChangeExpirationDetails struct
  - Add optional shared_content_link to SharedLinkSettingsChangePasswordDetails struct
  - Add optional shared_content_link to SharedLinkSettingsRemoveExpirationDetails struct
  - Add optional shared_content_link to SharedLinkSettingsRemovePasswordDetails struct
  - Add file_locking_status_changed_details to EventDetails union
  - Add rewind_folder_details to EventDetails union
  - Add legal_holds_export_cancelled_details to EventDetails union
  - Add legal_holds_export_downloaded_details to EventDetails union
  - Add legal_holds_export_removed_details to EventDetails union
  - Add create_team_invite_link_details to EventDetails union
  - Add delete_team_invite_link_details to EventDetails union
  - Add binder_add_page_details to EventDetails union
  - Add binder_add_section_details to EventDetails union
  - Add binder_remove_page_details to EventDetails union
  - Add binder_remove_section_details to EventDetails union
  - Add binder_rename_page_details to EventDetails union
  - Add binder_rename_section_details to EventDetails union
  - Add binder_reorder_page_details to EventDetails union
  - Add binder_reorder_section_details to EventDetails union
  - Add rewind_policy_changed_details to EventDetails union
  - Add team_sharing_whitelist_subjects_changed_details to EventDetails union
  - Add web_sessions_change_active_session_limit_details to EventDetails union
  - Add enterprise_settings_locking_details to EventDetails union
  - Add file_locking_lock_status_changed to EventType union
  - Add rewind_folder to EventType union
  - Add legal_holds_export_cancelled to EventType union
  - Add legal_holds_export_downloaded to EventType union
  - Add legal_holds_export_removed to EventType union
  - Add create_team_invite_link to EventType union
  - Add delete_team_invite_link to EventType union
  - Add binder_add_page to EventType union
  - Add binder_add_section to EventType union
  - Add binder_remove_page to EventType union
  - Add binder_remove_section to EventType union
  - Add binder_rename_page to EventType union
  - Add binder_rename_section to EventType union
  - Add binder_reorder_page to EventType union
  - Add binder_reorder_section to EventType union
  - Add rewind_policy_changed to EventType union
  - Add team_sharing_whitelist_subjects_changed to EventType union
  - Add web_sessions_change_active_session_limit to EventType union
  - Add enterprise_settings_locking to EventType union

  - Add TeamInviteDetails struct
  - Add InviteMethod union
  - Add LockStatus union
  - Add RewindPolicy union
  - Add FileLockingLockStatusChangedDetails struct
  - Add RewindFolderDetails struct
  - Add LegalHoldsExportCancelledDetails struct
  - Add LegalHoldsExportDownloadedDetails struct
  - Add LegalHoldsExportRemovedDetails struct
  - Add CreateTeamInviteLinkDetails struct
  - Add DeleteTeamInviteLinkDetails struct
  - Add BinderAddPageDetails struct
  - Add BinderAddSectionDetails struct
  - Add BinderRemovePageDetails struct
  - Add BinderRemoveSectionDetails struct
  - Add BinderRenamePageDetails struct
  - Add BinderRenameSectionDetails struct
  - Add BinderReorderPageDetails struct
  - Add BinderReorderSectionDetails struct
  - Add RewindPolicyChangedDetails struct
  - Add TeamSharingWhitelistSubjectsChangedDetails struct
  - Add WebSessionsChangeActiviteSessionLimitDetails struct
  - Add EnterpriseSettingsLockingDetails struct
  - Add FileLockingLockStatusChangedType struct
  - Add RewindFolderType struct
  - Add LegalHoldsExportCancelledType struct
  - Add LegalHoldsExportDownloadedType struct
  - Add LegalHoldsExportRemovedType struct
  - Add CreateTeamInviteLinkType struct
  - Add DeleteTeamInviteLinkType struct
  - Add BinderAddPageType struct
  - Add BinderAddSectionType struct
  - Add BinderRemovePageType struct
  - Add BinderRemoveSectionType struct
  - Add BinderRenamePageType struct
  - Add BinderRenameSectionType struct
  - Add BinderReorderPageType struct
  - Add BinderReorderSectionType struct
  - Add RewindPolicyChangedType struct
  - Add TeamSharingWhitelistSubjectsChangedType struct
  - Add WebSessionsChangeActiveSessionLimitType struct
  - Add EnterpriseSettingsLockingType struct
  - Added AccountState union
  - Added AccountLockOrUnlockedType struct
  - Added AccountLockOrUnlockedDetails struct
  - Added MemberSendInvitePolicy union
  - Added MemberSendInvitePolicyChangedType struct
  - Added MemberSendInvitePolicyChangedDetails struct
  - Added a new tag first_party_token_exchange to LoginMethod union
  - Added new tags account_lock_or_unlocked_details and member_send_invite_policy_changed_details to EventDetails union
  - Added new tags account_lock_or_unlocked and member_send_invite_policy_changed to EventType union
  - Added a new field file_size to FileOrFolderLogInfo and FileLogInfo struct
  - Added a new field file_count to FolderLogInfo struct
  - Add NoExpirationLinkGenCreateReportDetails, NoExpirationLinkGenReportFailedDetails, NoPasswordLinkGenCreateReportDetails, NoPasswordLinkGenReportFailedDetails, NoPasswordLinkViewCreateReportDetails, NoPasswordLinkViewReportFailedDetails, OutdatedLinkViewCreateReportDetails, OutdatedLnkViewReportFailedDetails structs to the EventDetails union
  - Add NoExpirationLinkGenCreateReportType, NoExpirationLinkGenReportFailedType, NoPasswordLinkGenCreateReportType, NoPasswordLinkGenReportFailedType, NoPasswordLinkViewCreateReportType, NoPasswordLinkViewReportFailedType, OutdatedLinkViewCreateReportType, OutdatedLinkViewReportFailedType structs to the EventType union
  - Add deprecated tag to was_linked_apps_truncated, was_linked_devices_truncated, was_link_shared_folders_truncated parameters in JoinTeamDetails struct
  - Added the EventTypeArg union

- Users Namespace:
  - Add file_locking to UserFeature union
  - Add file_locking to UserFeatureValue
  - Update example for UserFeaturesGetaluesBatchArg

  - Add FileLockingValue union

- Cloud Docs Namespace
  - added a new route property is_cloud_doc_auth indicating whether the endpoint is a Dropbox cloud docs endpoint which takes cloud docs auth token.
  - Add get_content, get_metadata, rename, unlock, and lock routes
  - Add corresponding args, results, and errors

- Shared Links Namespace
  - Update SharedLinkSettings example

- Stone CFG Namespace
  - Update auth type string patterns
  - Update host string patterns
  - Update style string patterns
  - Update select_admin_mode string patterns

- Team Secondary Mails Namespace:
  - Remove is_preview from route add, resend_verification_emails, and delete

- Team Members Namespace:
  - Update comment for retain_team_shares arg of MembersRemoveArg

3.1.3 (2019-12-17)
---------------------------------------------
- Fix mobile sign in bug.

3.1.2 (2019-12-14)
---------------------------------------------
- Account namespace:
  - Added set_profile_photo end point.
- Auth namespace:
  - Added route_access_denied to AuthError.
- Check namespace:
  - Added this namespace for authentication test
- Common namespace:
  - Added SecondaryEmail struct.
- Contacts namespace:
  - Added scope route attribute to delete_manual_contacts end point.
- Files namespace:
  - Added scope route attribute to the following end points:
    - get_metadata
    - list_folder/longpoll
    - list_folder
    - list_folder/continue
    - list_folder/get_latest_cursor
    - download
    - download_zip
    - export
    - upload_session/start
    - upload_session/append
    - upload_session/append:2
    - upload_session/finish
    - upload_session/finish_batch
    - upload_session/finish_batch/check
    - search
    - upload
    - create_folder
    - create_folder:2
    - create_folder_batch
    - create_folder_batch/check
    - delete
    - delete:2
    - delete_batch
    - delete_batch/check
    - permanently_delete
    - copy
    - copy:2
    - copy_batch
    - copy_batch:2
    - copy_batch/check
    -  copy_batch/check:2
    - move
    - move:2
    - move_batch
    - move_batch:2
    - move_batch/check:2
    - move_batch/check
    - get_thumbnail
    - get_thumbnail_batch
    - get_preview
    - list_revisions
    - restore
    - get_temporary_link
    - get_temporary_upload_link
    - copy_reference/get
    - copy_reference/save
    - save_url
    - save_url/check_job_status
  - Added new search:2 end point.
  - Added new search/continue:2 end point
  - Added new lock_file_batch end point
  - Added new unlock_file_batch end point
  - Added new get_file_lock_batch end point
  - Added New MetadataV2 union
  - Added new HighlightSpan struct
  - Added new FileLockMetadata struct
  - Added file_lock_info to FileMetadata struct
  - Added template_error to ListFolderError union
  - Added retry_error to ExportError union
- File_properties namespace:
  - Added scope route attribute to to the following end points:
    - properties/add
    - properties/overwrite
    - properties/update
    - properties/remove
    - properties/search
    - templates/add_for_user
    - templates/add_for_team
    - templates/get_for_user
    - templates/get_for_team
    - templates/update_for_user
    - templates/update_for_team
    - templates/list_for_user
    - templates/list_for_team
    - templates/remove_for_user
    - templates/remove_for_team
- File_requests namespace:
  - Added optional scope route attribute to to the following end points:
    - list:2
    - list/continue
    - list
    - get
    - create
    - update
    - count
    - delete
    - delete_all_closed
  - Updated docstrings for CreateFileRequestError
- Team namespace:
  -  Added scope route attribute to to the following end points:
    -  legal_holds/release_policy
    -  members/secondary_emails/add
    -  members/secondary_emails
    - get_info
    - token/get_authenticated_admin
    - features/get_values
    - devices/list_member_devices
    - devices/list_members_devices
    - devices/revoke_device_session
    - devices/revoke_device_session_batch
    - team_folder/create
    - team_folder/rename
    - team_folder/list
    - team_folder/list/continue
    - team_folder/get_info
    - team_folder/activate
    - team_folder/archive
    - team_folder/archive/check
    - team_folder/permanently_delete
    - groups/list
    - groups/list/continue
    - groups/get_info
    - groups/create
    - groups/delete
    - groups/update
    - groups/members/add
    - groups/members/remove
    - groups/members/set_access_type
    - groups/members/list
    - groups/members/list/continue
    - linked_apps/list_member_linked_apps
    - linked_apps/list_members_linked_apps
    - linked_apps/revoke_linked_app
    - linked_apps/revoke_linked_app_batch
    - member_space_limits/set_custom_quota
    - member_space_limits/remove_custom_quota
    - member_space_limits/get_custom_quota
    - member_space_limits/excluded_users/add
    - member_space_limits/excluded_users/remove
    - member_space_limits/excluded_users/list
    - members/list
    - members/list/continue
    - members/get_info
    - members/add
    - members/add/job_status/get
    - members/set_admin_permissions
    - members/send_welcome_email
    - members/remove
    - members/remove/job_status/get
    - members/suspend
    - members/unsuspend
    - members/recover
    - members/move_former_member_files
    - namespaces/list
    - namespaces/list/continue
    - reports/get_storage
    - reports/get_activity
    - reports/get_membership
  - Added new legal_holds/release_policy end point.
  - Added new members/secondary_emails/add end point.
  - Added new members/secondary_emails/resend_verification_emails
  - Added new members/secondary_emails/delete end point
  - Added new members/set_profile_photo end point
  - Added new members/delete_profile_photo end point
  - Added secondary_emails to MemberProfile struct
  - Added invited_on to MemberProfile struct
  - Added retain_team_shares in MembersRemoveArg Struct
  - Added the following to MembersRemoveError union
    - cannot_retain_shares_when_data_wiped
    - cannot_retain_shares_when_no_account_kept
    - cannot_retain_shares_when_team_external_sharing_off
    - cannot_keep_account
    - cannot_keep_account_under_legal_hold
    - cannot_keep_account_required_to_sign_tos
  - Updated docstring for DateRange
- Team_log namespace:
  - Add scope route attribute to the following end points:
    - get_events
  - Added unlink_device to QuickActionType union
  - Added enterprise_console to AccessMethodLogInfo
  - Added was_linked_apps_truncated, was_linked_devices_truncated, was_linked_shared_folders_truncated to JoinTeamDetails struct
  - Added web_session, qr_code, apple_oauth to LoginMethod union
  - Added enterprise_admin to TrustedNonTeamMemberType union
  - Added team to TeamMemberLogInfo struct
  - Added is_shared_namespace to NamespaceRelativePathLogInfo struct
  - Added organization_team to ContextLogInfo union
  - Added legal_holds to EventCategory union
  - Added notification_type to AccountCaptureNotificationEmailsSentDetails struct
  - Added the following to EventDetails union:
    - folder_overview_description_changed_details
    - folder_overview_item_pinned_details
    - folder_overview_item_unpinned_details
    - legal_holds_activate_a_hold_details
    - legal_holds_add_members_details
    - legal_holds_change_hold_details_details
    - legal_holds_change_hold_name_details
    - legal_holds_export_a_hold_details
    - legal_holds_release_a_hold_details
    - legal_holds_remove_members_details
    - legal_holds_report_a_hold_details
    - member_delete_profile_photo_details
    - member_set_profile_photo_details
    - pending_secondary_email_added_details
    - secondary_email_deleted_details
    - secondary_email_verified_details
    - paper_published_link_change_permission_details
    - export_members_report_fail_details
    - file_transfers_file_add_details
    - file_transfers_transfer_delete_details
    - file_transfers_transfer_download_details
    - file_transfers_transfer_send_details
    - file_transfers_transfer_view_details
    - shared_content_restore_invitees_details
    - shared_content_restore_member_details
    - device_approvals_add_exception_details
    - device_approvals_remove_exception_details
    - file_locking_policy_changed_details
    - file_transfers_policy_changed_details
    - password_strength_requirements_change_policy_details
    - smarter_smart_sync_policy_changed_details
    - tfa_add_exception_details
    - tfa_remove_exception_details
    - watermarking_policy_changed_details
    - changed_enterprise_admin_role_details
    - changed_enterprise_connected_team_status_details
    - ended_enterprise_admin_session_details
    - ended_enterprise_admin_session_deprecated_details
    - started_enterprise_admin_session_details
    - shared_link_settings_add_expiration_details
    - shared_link_settings_add_password_details
    - shared_link_settings_allow_download_disabled_details
    - shared_link_settings_allow_download_enabled_details
    - shared_link_settings_change_audience_details
    - shared_link_settings_change_expiration_details
    - shared_link_settings_change_password_details
    - shared_link_settings_remove_expiration_details
    - shared_link_settings_remove_password_details
  - Added the following to EventType union:
    - folder_overview_description_changed
    - folder_overview_item_pinned
    - folder_overview_item_unpinned
    - legal_holds_activate_a_hold
    - legal_holds_add_members
    - legal_holds_change_hold_details
    - legal_holds_change_hold_name
    - legal_holds_export_a_hold
    - legal_holds_release_a_hold
    - legal_holds_remove_members
    - legal_holds_report_a_hold
    - member_delete_profile_photo
    - member_set_profile_photo
    - pending_secondary_email_added
    - secondary_email_deleted
    - secondary_email_verified
    - paper_published_link_change_permission
    - export_members_report_fail
    - file_transfers_file_add
    - file_transfers_transfer_delete
    - file_transfers_transfer_download
    - file_transfers_transfer_send
    - file_transfers_transfer_view
    - shared_content_restore_invitees
    - shared_content_restore_member
    - device_approvals_add_exception
    - device_approvals_remove_exception
    - file_locking_policy_changed
    - file_transfers_policy_changed
    - password_strength_requirements_change_policy
    - smarter_smart_sync_policy_changed
    - tfa_add_exception
    - tfa_remove_exception
    - watermarking_policy_changed
    - changed_enterprise_admin_role
    - changed_enterprise_connected_team_status
    - ended_enterprise_admin_session
    - ended_enterprise_admin_session_deprecated
    - started_enterprise_admin_session
- Team_policies namespace:
  - Added disabled in TwoStepVerificationState union
  - Added new unions PasswordControlMode, SmarterSmartSyncPolicyState, FileLockingPolicyState
- Paper namespace:
  - Updated doctoring for the namespace
  - Updated doctoring for PaperApiBaseError
  - Added PaperFolderCreateArg, PaperFolderCreateResult structs
  - Added new PaperFolderCreateError union
  - Updated docstring for following end points:
    - docs/folder_users/list
    - docs/folder_users/list/continue
    - docs/sharing_policy/get
    - docs/sharing_policy/set
    - docs/archive
    - docs/permanently_delete
    - docs/download
    - docs/get_folder_info
    - docs/users/add
    - docs/users/remove
    - docs/users/list
    - docs/users/list/continue
    - docs/list
    - docs/list/continue
    - docs/create
    - docs/update
    - folders/create
  -  Added scope route attribute to the following end points:
    - docs/folder_users/list
    - docs/folder_users/list/continue
    - docs/sharing_policy/get
    - docs/sharing_policy/set
    - docs/archive
    - docs/permanently_delete
    - docs/download
    - docs/get_folder_info
    - docs/users/add
    - docs/users/remove
    - docs/users/list
    - docs/users/list/continue
    - docs/list
    - docs/list/continue
    - docs/create
    - docs/update
- Sharing namespace:
   Add scope route attribute to the following end points:
    - get_shared_link_metadata
    - list_shared_links
    - modify_shared_link_settings
    - create_shared_link_with_settings
    - revoke_shared_link
    - get_shared_link_file
    - add_file_member
    - update_file_member
    - get_file_metadata
    - get_file_metadata/batch
    - list_file_members
    - list_file_members/batch
    - list_file_members/continue
    - list_received_files
    - list_received_files/continue
    - remove_file_member
    - remove_file_member_2
    - relinquish_file_membership
    - unsharp_file
    - list_folders
    - list_folders/continue
    - list_mountable_folders
    - list_mountable_folders/continue
    - get_folder_metadata
    - list_folder_members
    - list_folder_members/continue
    - share_folder
    - check_share_job_status
    - check_job_status
    - unsharp_folder
    - transfer_folder
    - update_folder_policy
    - add_folder_member
    - remove_folder_member
    - check_remove_member_job_status
    - update_folder_member
    - mount_folder
    - unmount_folder
    - relinquish_folder_membership
    - set_access_inheritance
  - Add parent_folder_name to SharedFolderMetadataBase
- Users namespace:
    - Added scope route attribute to the following end points:
      - get_account
      - get_current_account
      - get_space_usage
      - get_account_batch
    - Added user_within_team_space_used_cached to TeamSpaceAllocation struct
    - Added new features/get_values end point

3.1.1 (2019-6-17)
---------------------------------------------
- Fix Fix protocol and ciphersuite selection to enable TLSv1.2 and TLSv1.1
- Update to Latest API specs:
  File namespace:
  - Added new ExportInfo struct
  - Added new fields (is_downloadable, export_info) to FileMetadata
  - Added new include_non_downloadable_files to ListFolderArg
  - Added new ExportMetadata, ExportArg, Export Result Structs
  - Added new ExportError union
  - Added new /export route

  Sharing namespace:
  - Added password field to LinkAudience
  - Added effective_audience and link_access_level fields to LinkPermissions struct
  - Updated docstrings for LinkPermissions
  - Added audience and access fields to SharedLinkSettings struct
  - New LinkAccessLevel and RequestedLinkAccessLevel union
  - Added new create_view_link and create_edit_link fields to FileAction union

  Team_log namespace:
  - New types added

  Team_policies namespace:
  - New TwoStepVerificationState union

  Team_reports namespace:
  - New TemporaryFailureReason union added.

3.1.0 (2019-5-6)
---------------------------------------------
- Early Access on Short-live token feature.
- Update to Latest API specs:
  Auth Namespace:
  - Add missing_scope into AuthError

  File_requests namespace:
  - Add list and list/continue endpoints.
  - Add count endpoint.
  - Add delete and delete_all_closed endpoints.

  Files namespace:
  - Add unsupported_file to DownloadError.
  - Add upper bound 9999 to start field in SearchArg.
  - Add unsupported_content_type to LookupError.
  - Add cant_move_shared_folder to RelocationError.
  - Add email_not_verified and unsupported_file to GetTemporaryLinkError.

  Seen_state namespace:
  - Add mobile_ios, mobile_android and api into PlatformType.
  - deprecate mobile in PlatformType.

  Sharing namespace:
  - Change shared_link_already_exists under CreateSharedLinkWithSettingsError from void to SharedLinkAlreadyExistsMetadata.
  - Add banned_member to AddFolderMemberError.

  Team namespace:
  - Add profile_photo_url and suspended_on into MemberProfile.

  Team_log namespace:
  - Add reset_password and restore_file_or_folder to QuickActionType.
  - Add google_oauth to LoginMethod.
  - Add australia_only and japan_only to PlacementRestriction.
  - Add trusted_teams to EventCategory.
  - In event details.
    - Add integration_connected_details.
    - Add integration_disconnected_details.
    - Add file_request_delete_details.
    - Add guest_admin_signed_in_via_trusted_teams_details.
    - Add guest_admin_signed_out_via_trusted_teams_details.
    - Add member_add_external_id_details.
    - Add member_change_external_id_details.
    - Add member_remove_external_id_details
    - Add integration_policy_changed_details.
    - Add paper_default_folder_policy_changed_details.
    - Add paper_desktop_policy_changed_details.
    - Add team_extensions_policy_changed_details.
    - Add guest_admin_change_status_details.
  - In EventType
    - Add integration_connected.
    - Add integration_disconnected.
    - Add file_request_delete.
    - Add guest_admin_signed_in_via_trusted_teams.
    - Add guest_admin_signed_out_via_trusted_teams.
    - Add member_add_external_id.
    - Add member_change_external_id.
    - Add member_remove_external_i.
    - Add integration_policy_change.
    - Add paper_default_folder_policy_change.
    - Add paper_desktop_policy_changed.
    - Add team_extensions_policy_changed.
    - Add guest_admin_change_status.

  stone_cfg:
  Add scope into route attribute.

3.0.11 (2018-12-12)
---------------------------------------------
- Update to Latest API specs:
  - Common Namespace:
    - Allow DisplayNameLegacy to support a name of zero chars
    - Force matching dot character in alias EmailAddress
  - File_properties namespace:
    - Doesn’t allow app folder app to access file property endpoints.
  - Files namespace:
    - Create copy_batch:2 and move_batch:2 endpoints. Deprecate existing copy_batch and move_batch.
  - Contacts namespace:
    - New namespace
    - New routes: delete_manual_contacts and delete_manual_contacts_batch
    - New argument structs for new routes
  - Sharing namespace:
    - Add no_one option to LinkAudience union
  - Sharing_files namespace:
    - Doesn’t allow app folder app to access sharing files endpoints.
  - Teams namespace:
    - Add is_disconnected boolean to RemovedStatus struct
    - Add error response type to namespace/list route
    - Only Team apps with Team member file access can access team/properties endpoints.
  - Team_log namespace:
    - New event types added

3.0.10 (2018-10-11)
---------------------------------------------
- Update to Latest API specs:
  - Files Namespace:
    - Updated doc strings.
  - Team_log Namespace:
    - Updated event docstrings.
    - New reset field for loading events with a cursor.
    - New event types added.
  - Team_policies Namespace:
    - New CameraUploadsPolicyState union.

3.0.9 (2018-09-15)
---------------------------------------------
- Update to Latest API specs:
  - files namespace:
    - Increased size limit for download_zip endpoint.
    - Update documentation for data transport call limit.
    - Added get_temporary_upload_link endpoint.
  - paper namespace:
    - Added invite_editor to FileAction.
    - Added access_inheritance to MembershipInfo.
  - team_log namespace:
    - Added more event types and details.
  - team:
    - Added members/move_former_member_files endpoint.
    - Added members/move_former_member_files/job_status/check endpoint.
- Add ProgressListener to upload and download.
- Change to include team_id field in auth finish class

3.0.8 (2018-05-22)
---------------------------------------------
- Update to Latest API specs:
  - Namespace Files:
    - Added new too_large error type for uploads.
    - New documentation.
  - Namespace Team:
    - Add is_directory_restricted attribute to memberprofile, memberaddarg.
    - Add new_is_directory_restricted to membersetprofilearg.
  - Namespace Team_log:
    - Additional documentation.
- Add asAdmin to DbxTeamClientV2.
- Support SSL_* ciphers in ALLOWED_CIPHER_SUITES.

3.0.7 (2018-04-13)
---------------------------------------------
- Update to Latest API specs:
  - Namespace file_properties:
    - Updated comments.
  - Namespace files:
    - Added parent_rev attribute to deletearg.
    - Added select_admin_mode attribute to relevant routes.
    - Added too_many_write_operations error type to writeerror.
    - New createfolderbatch endpoint and related datatypes.
    - New fileid alias.
    - New symlinkinfo struct on filemetadata.
    - New syncsettings objects.
    - New thumbnail sizes.
    - New thumbnailmode object.
  - Namespace seen_state:
    - New namespace.
  - Namespace sharing:
    - Add seen_state.platformtype to userfilemembershipinfo.
    - Added select_admin_mode attribute to relevant routes.
    - Additional user info added to userinfo struct.
    - New accessinheritance union.
    - New set_access_inheritance for folderaction.
    - New set_access_inheritance route.
    - Updated docs.
  - Namespace team:
    - Add additional error types to membersremoveerror union.
    - New hasteamselectivesync object.
    - New selective sync settings included in various return objects and error types.
    - New update_sync_settings route.
    - Updated docstring.
    - Updated docstrings.
  - Namespace team_common:
    - Added new memberspacelimittype union.
  - Namespace team_log:
    - Lots of updates to struct names and descriptions (note these routes and structs are still in preview and subject to further changes).
    - Updated event types.
  - Namespace team_policies:
    - New showcasedownloadpolicy object.
    - New showcaseenabledpolicy object.
    - New showcaseexternalsharingpolicy object.
  - Namespace users:
    - Additional member space limit fields in teamspaceallocation struct.
    - Updated routes with select_admin_mode attribute.
- Add withPathRoot to DbxClientV2.
- Make Android and GAE optional in OSGI Import-Package statements.

3.0.6 (2018-01-14)
---------------------------------------------
- Update to Latest API specs:
  - Namespace common:
    - New LanguageCode alias.
  - Namespace file_properties:
    - Updated docstrings.
  - Namespace file_requests:
    - Updated docstrings.
  - Namespace files:
    - New aliases and structs relating to shared links.
    - Move shared_link to end of parameter list for ListFolderArg.
    - Add mode to ListRevisionsArg.
  - Namespace sharing:
    - New UserFileMembershipInfo struct.
  - Namespace team_folders:
    - Updated doc strings.
    - Additional async example.
  - Namespace team_log:
    - New TeamEventList alias.
    - New autogenerated datatypes.
  - Namespace team_policies:
    - New TwoStepVerificationPolicy.

3.0.5 (2017-10-07)
---------------------------------------------
- Update to Latest API specs:
  - Namespace common:
    - new LanguageCode alias.
  - Namespace file_properties:
    - Updated docstrings.
  - Namespace file_requests:
    - Updated docstrings.
  - Namespace files:
    - New aliases and structs relating to shared links.
    - Move shared_link to end of parameter list for ListFolderArg.
    - Add mode to ListRevisionsArg.
  - Namespace sharing:
    - New UserFileMembershipInfo struct.
  - Namespace team_folders:
    - updated doc strings.
    - additional async example.
  - Namespace team_log:
    - new TeamEventList alias.
    - new autogenerated datatypes.
  - Namespace team_policies:
    - new TwoStepVerificationPolicy.

3.0.4 (2017-09-19)
---------------------------------------------
- Update to Latest API specs:
  - General:
    - Numerous updates to docstrings across all namespaces.
    - Updated general route configuration to support select_admin_mode.
  - Auth, Users, TeamReports, TeamPropertyTemplates, TeamDevices, TeamGroups, TeamLinkedApps Namespaces:
    - Update route ownership.
  - Common Namespace:
    - Fix regular expression for DisplayName.
    - Rename shared_folder to namespace_id for path root header.
    - New aliases for OptionalNamePart and DisplayNameLegacy.
  - Files Namespace:
    - Clarify `WriteMode` documentation.
    - Add Select-Admin badge to docs, remove list from business page.
    - Support fileId for move api v2 endpoints.
    - API_V2 delete_batch should grab one ns_lock when processing one namespace instead of holding all locks at beginning.
    - Add FileId support to list_folder.
    - Added changeset support for fileops and /rollback endpoint.
    - Change default of allow_ownership_transfer to false.
    - Get double the limit in list_revisions to include deleted and truncate later in controller.
    - Add server_deleted timestamp to list_revisions.
    - Revert changes to api delta that aren't backwards compatible.
    - Add deleted_at to DeletedMetadata in list_folders, get_metadata. Add deleted_at to toplevel response,
      add include_deleted as param in list_revisions.
    - Update ownership.
    - New attributes for ListFolderArg: included_mounted_folders, limit.
    - New get_thumbnail_batch route and corresponding interfaces.
  - SharedContentLinks Namespace:
    - API changes for child exceptions.
  - SharedLinks Namespace:
    - Add max results limit of 1000 for /2/sharing/get_shared_links.
    - Update sharing route ownership.
    - Add link to list_shared_links in shared_link_already_exists error.
  - SharingFiles Namespace:
    - Add owner name as a new field to alpha sharing file metadata.
  - SharingFolders Namespace:
    - Make the internal endpoint take internal folder actions.
    - Update route ownership.
    - Added owner_display_names to SharedFolderMetadataBase.
    - Updated PermissionDeniedReason union.
  - StoneCfg Namespace:
    - Add Select-Admin badge to docs, remove list from business page.
    - Update route ownership.
  - Team Namespace:
    - Enable looking up if a team is in CDM.
    - Update route generator to pass through team endpoint ownership.
    - Update route ownership.
    - Add route member_space_limits/set_custom_quota.
    - Add route member_space_limits/remove_cusom_quota.
    - Add route member_space_limits/get_custom_quota.
    - Deprecate beta properites routes.
  - TeamFolders Namespace:
    - Update team folder APIs with some extra fields.
    - Update route ownership.
  - TeamLog Namespace:
    - Start using v2 category index.
    - Reduced strictness of pattern matching for IpAddress.
    - New FileCommentNotificationPolicy union
    - Multiple updated attribute names in unions.
    - New Structs for new team_log objects
  - TeamLogGenerated Namespace:
    - Variable scheme for team events.
    - Mark ACCOUNT_CAPTURE_NOTIFICATION_EMAILS_SENT event as under development.
    - Make sure team policies event expose their own union (for API future proofing).
    - Add device_info as data_gap for 2 event types.
    - Save group info into participants field.
    - Account capture pro-active email notifications - audit log.
    - Fix schema of member_change_membershipe_type and member_space_limits_change_status.
    - Make team_folder_change_status conform to previous_value/new_value convention.
    - Fixes the variable schema of domain verification and account capture event types.
    - Use common.Data stone type for the variable schema fields of team_activity_create_report.
    - Introduce a new struct for team name.
    - Fix comments related to sso events.
  - TeamMembers Namespace:
    - Return root ns_id on some call.
    - Update ownership.
    - Update NamePart? to be OptionalNamePart?.
  - TeamNamespaces Namespace:
    - Implement API V2 route team/namespaces/list.
  - TeamPolicies Namespace:
    - Add Office Add-In Policy to `get_current_account` return.
    - Add new team policies for SSO Paper, RolloutMethod and PasswordStrength.
  - Paper Namespace:
    - New "docs/create" and "docs/update" routes and corresponding interfaces.
  - File_properties Namespace:
    - New routes and structs for the file properties and templates API functionality.
  - File_requests Namespace:
    - New routes and structs for the file_requests API functionality.
  - Files_properties Namespace:
    - removed in favor of file_properties.
  - Properties Namespace:
    - removed in favor of file_properties.
  - Team_property_templates Namespace:
    - removed in favor of file_properties.
- Add global response handlers.
- Add PathRootErrorException and AccessErrorException corresponding to 422 and 403 status codes.
- Add support for map data type in stone.
- Fix upload hanging in OKHttp3 when internet is cut off.

3.0.3 (2017-05-02)
---------------------------------------------
Fix the compatibility bug that cause sharing/get_file_metadata to crash.

3.0.2 (2017-04-11)
---------------------------------------------
- Update to latest API specs:
  - Auth namespace:
    - Added TokenFromOAuth1Arg, TokenFromOAuth1Result and TokenFromOAuth1Error.
    - Added token/from_oauth1 rote.
    - Added AccessError and PaperAccessError.
    - Added InvalidAccountTypeError.
  - Files namespace:
    - Added UploadSessionFinishBatchLaunch and made it new return type for upload_session/finish_batch.
    - Added Sha256HexHash alias.
    - Added content_hash to FileMetadata.
    - Added upload_api_rate_limit feature attribute to upload_session/start, upload_session/append_v2, upload_session/append, upload, upload_session/finish_batch.
    - Added duplicated_or_nested_paths to RelocationError and removed from RelocationBatchError.
    - Added properties api_group attribute and is_preview attribute to properties/*.
    - Added disable_viewer_info and enable_viewer_info to CommitInfoWithProperties.
    - Added link_metadata to SharedFileMetadata.
    - Added ViewerInfoPolicy union.
    - Added no_explicit_access to MemberSelector.
    - Deprecated change_file_member_access.
    - Added update_file_member route and UpdateFileMemberArgs struct.
  - Sharing namespace:
    - Added unsupported_link_type to SharedLinkError.
    - Added is_member to GroupInfo.
    - Added too_many_files to UnshareFolderError.
    - Added no_explicit_access to RelinquishFolderMembershipError.
    - Added viewer_info_policy, disable_viewer_info, enable_viewer_info to FolderPolicy.
    - Added team, is_inside_team_folder, path_lower to SharedLinkPolicy.
    - Added link_metadata, policy, shared_folder_id, time_invited to SharedFolderMetadata.
    - Added actions, link_settings, viewer_info_policy to ShareFolderArg and removed default values from policies in ShareFolderArg.
    - Added viewer_info_policy, link_settings to UpdateFolderPolicyArg.
  - Stone Cfg namespace:
    - Added feature route attribute.
    - Added attribute api_group, is_preview.
    - Removed attributes alpha_group, beta_group.
  - Team namespace:
    - Added group_name_already_used and group_name_invalid to GroupUpdateError.
    - Added joined_on, persistent_id to MemberProfile.
    - Added team_member_id, external_id to UserSelectorArg.
    - Added TeamMemberId, MemberExternalId, GroupExternalId, ResellerId aliases.
    - Added company_managed, system_managed to GroupManagementType.
    - Added TimeRange.
    - Added archive_in_progress to TeamFolderStatus, TeamFolderIdArg.
    - Added BaseTeamFolderError.
    - TeamFolderRenameError, TeamFolderArchiveError, BaseTeamFolderError, TeamFolderPermanentlyDeleteError now extend BaseTeamFolderError.
    - Added folder_name_reserved to TeamFolderRenameError.
    - Added GroupSelectorWithTeamGroupError.
    - GroupMemberSelectorError, GroupMembersSelectorError now extends GroupSelectorWithTeamGroupError.
    - Removed alpha from alpha/groups/*.
    - GroupDeleteError, GroupUpdateError, GroupMembersAddError now extends GroupSelectorWithTeamGroupError.
    - Added members_not_in_team, users_not_found to GroupMembersAddError.
    - Added joined_on to TeamMemberProfile.
    - Added member_persistent_id, duplicate_member_persistent_id, persistent_id_disabled, new_persistent_id, persistent_id_disabled, persistent_id_used_by_other_user to MemberSelectorError.
3.0.1 (2017-03-29)
---------------------------------------------
- Add OpenWith support for official partners.

3.0.0 (2017-03-17)
---------------------------------------------
- Breaking changes:
  - static INSTANCE is removed from OkHttp3Requestor and OkHttpRequestor
  - copyBatch/moveBatch now takes RelocationBatchArg instead of List<RelocationPath>
- Update to latest API specs:
  - Auth namespace:
    - Added user_suspended to AuthError.
  - Files namespace:
    - Added PathRootError.
    - Added invalid_path_root to LookupError.
    - Added autorename to CreateFolderArg.
    - Added DeleteBatchArg, DeleteBatchResultEntry, DeleteResult, DeleteBatchResult, DeleteBatchError, DeleteBatchJobStatus and DeleteBatchLaunch.
    - Added delete_batch and delete_batch/check routes.
    - Added RelocationPath.
    - Added to allow_shared_folder and autorename to RelocationArg.
    - Added RelocationBatchArg, RelocationBatchResult, RelocationBatchJobStatus, RelocationResult,RelocationBatchError and RelocationBatchLaunch.
    - Added copy_batch and copy_batch/check routes.
    - Added move_batch and move_batch/check routes.
  - Sharing namespace:
    - Changed PathOrId validation pattern.
    - Changed path in ShareFolderArg from type files.Path to files.WritePath.
    - Added contains_app_folder, contains_team_folder and invalid_path_root to ShareFolderArg.
  - Stone Cfg namespace:
    - Changed validation pattern for owner in Route.
    - Added feature route attribute.
  - Team namespace:
    - Added team_license_limit to MembersRecoverError.
    - Removed beta_group attribute from members/recover.
- Fix the bug that when InputStream throws IOException, DbxUploader#uploadAndFinish() throws NetworkIOException

2.1.1 (2016-08-01)
---------------------------------------------
- Fix "Required field ... missing" deserialization bug caused by certain backwards-compatible response changes from the server.

2.1.0 (2016-07-29)
---------------------------------------------
- Update to latest API specs:
  - Files
    - Add uploadSessionFinishBatch(..) endpoint for batch uploads.
  - Sharing:
    - Add changeFileMemberAccess(..) for changing a member's access to a shared file.
    - Add INVITE_VIEWER_NO_COMMENT and SHARE_LINK to FolderAction.
    - Add MemberAction.MAKE_VIEWER_NO_COMMENT.
    - Add preview URL to SharedFolderMetadata.
    - Add parent folder access information to MemberAccessLevelResult.
    - Add AddFolderMemberError.TOO_MANY_INVITEES.
    - Add AddMemberSelectorError.AUTOMATIC_GROUP.
    - Add MountFolderError.INSUFFICIENT_QUOTA.
  - Team:
    - Add TeamMemberStatus.Tag.REMOVED.
    - Add ability to update group management type for a group.
    - Add ability to include removed members when listing members of a team.
    - Add membersRecover(..) endpoint for recovering team members.
- Fix OkHttpRequestor/OkHttp3Requestor to support interceptors that consume request bodies, like Stetho.
  - Fix does not apply to streaming uploads.
- Fix OkHttpRequestor/OkHttp3Requestor to properly handle streaming uploads.
  - The requestors no longer buffer entire request body in memory for streams.
- Add configureRequest(..) method for simpler subclassing of OkHttpRequestor and OkHttp3Requestor.
- Fix BadRequest error when adding custom state to a DbxWebAuth.Request object.
- Remove final modifier from DbxClientV2 and DbxTeamClientV2 class declarations for easier mocking in tests.

2.0.6 (2016-06-20)
---------------------------------------------
- Update to latest API specs:
  - Files (DbxUserFilesRequests)
    - Add file properties endpoints.
  - Sharing (DbxUserSharingRequests)
    - Add endpoints for sharing files and managing shared file membership.
    - Change return type of removeFolderMember(..) endpoint to always be an async Job ID (LaunchEmptyResult.isAsyncJobId() will be true).
    - Add checkRemoveMemberJobStatus(..) for checking asynchronous removeFolderMember(..) requests.
      - Returns additional information compared to checkJobStatus(..)
    - Change return type of updateFolderMember(..) to return a MemberAccessLevelResult instead of void.
    - Add NO_EXPLICIT_ACCESS to UpdateFolderMemberError.
- Fix Android Fake ID exploit where app certificate chains aren't properly validated.

2.0.5 (2016-06-08)
---------------------------------------------
- Allow old locale formats for APIv2 requests.
- Fix ExceptionInInitializationError caused by CertificateParsingException when using Java 6 JREs.
- Fix CertPathValidatorException: Trust anchor for certification path not found.
- Add support for OkHttp3.
- Add support for Google App Engine with new GoogleAppEngineRequestor.
- Add support for require_role, force_reapprove, state, and disable_signup parameters in the OAuth 2 web-based authorization flow (DbxWebAuth).
- Enable certificate pinning for OkHttpRequestor and OkHttp3Requestor by default.

2.0.4 (2016-05-31)
---------------------------------------------
- Update to latest API specs:
  - Files (DbxUserFilesRequests)
    - Add saveUrl(..) saving online content to your Dropbox.
  - Shared folders (DbxUserSharingRequests)
    - Add AccessLevel.VIEWER_NO_COMMENT.
    - Add GroupInfo.getIsOwner().
    - Change return type of SharePathError.Tag.ALREADY_SHARED from Void to SharedFolderMetadata.
    - Add leaveACopy argument to relinquishFolderMembership(..).
    - Change relinquishFolderMembership(..) to return async job ID when leaving a copy.
    - Add JobError.Tag.RELINQUISH_FOLDER_MEMBERSHIP_ERROR.
  - Business endpoints (DbxTeamTeamRequests)
    - Add MemberProfiler.getMembershipType().
    - Add keepAccount argument to membersRemove(..).
    - Add CANNOT_KEEP_ACCOUNT_AND_TRANSFER and CANNOT_KEEP_ACCOUNT_AND_DELETE_DATA to MembersRemoveError.
- Migrate build from maven to gradle.
- Improve code shrinking when using ProGuard.
  - Response/request serialization updated to be better optimized by ProGuard.
- Properly support multidex builds.
  - Response/request objects should no longer always be kept in primary dex.
- Add partial download support through range requests.
- Fix deserialization bug when handling new server responses that were previously void.
- Fix bug where user locale is ignored for APIv2 requests.
- Fix bug where filenames containing line feeds were rejected as bad requests.

---------------------------------------------
2.0.3 (2016-05-07)
- Fix Bad JSON error on ProGuard optimized APKs when deserializing error responses.
  - All 2.0.x versions before 2.0.3 are affected and should be upgraded immediately.
  - Only affects Android apps that enable ProGuard.
  - Affected apps may crash when deserializing an error response from Dropbox servers.

---------------------------------------------
2.0.2 (2016-04-28)
- Update to latest API specs:
  - Authentication
    - Add token/revoke endpoint.
  - Account
    - Add disabled field to Account.
  - Files (DbxUserFilesRequests)
    - Add withIncludeDeleted(Boolean) and withIncludeHasExplicitSharedMembers(Boolean) to GetMetadataBuilder and ListFolderBuilder.
    - Add close argument to uploadSessionStart(..) to explicitly close an upload session.
    - Add uploadSessionAppendV2(..) that provides explicit session close support. uploadSessionAppend(..) is now deprecated.
    - Add copyReferenceGet(..) and copyReferenceSave(..) for copying files and folders.
    - Add getTemporaryLink(..) endpoint.
  - Shared links (DbxUserSharingRequests)
    - Add removeExpiration argument to modifySharedLinkSettings(..).
  - Shared folders
    - Add FolderAction.LEAVE_A_COPY.
    - Add SharedFolderMetadata.getTimeInvited().
    - Add IS_OSX_PACKAGE and INSIDE_OSX_PACKAGE to SharePathError. Returned when a user attempts to share an OS X package or folder inside an OS X package.
  - Business endpoints (DbxTeamTeamRequests)
    - GroupSummary.getMemberCount() is now optional and returns a Long.
    - devicesListTeamDevices(..) is now deprecated by devicesListMemberDevices(..).
    - linkedAppsListTeamLinkedApps(..) is now deprecated by linkedAppsListMembersLinkedApps(..).
    - Add returnMembers argument to groupsMembersSetAccessType(..).
- Fix JsonDateReaderTest failures for non-English systems.
- Update ProGuard rules to fix handling of embedded trusted SSL certs resource.
- Fix tutorial example to list folder entries for folders with many files.

---------------------------------------------
2.0.1 (2016-03-09)
- Update to latest API specs:
  - Update documentation.
  - Add FolderPolicy.getResolvedMemberPolicy()
  - Add GroupInfo.getGroupType()
  - Add SharedFolderMetadataBase.getOwnerTeam()
  - Add SharedFolderMetadataBase.getParentSharedFolderId()
  - Add MountFolderError.NOT_MOUNTABLE
  - Add UmountFolderError.NOT_UNMOUNTABLE
  - Add validation for member external id and email address
  - Add TeamSharingPolicies.getSharedLinkCreatePolicy()
  - Add MembersSuspendError.TEAM_LICENSE_LIMIT
  - Add MembersUnsuspendError.TEAM_LICENSE_LIMIT
- Fix bug when deserializing v2 data types with missing optional primitive fields.
- Fix bug where some Date objects were not being properly truncated to seconds granularity in v2
  data types.
- Fix v2 timestamp parsing to support DateTime and Date formats.
- Add support for Dropbox API app endpoints.
- Update upload-file example to include chunked upload example.
- Increase default socket read timeout to 2 minutes.
- Parse Retry-After header for 503 retry exceptions in API v1.
- Add example from online tutorial.

---------------------------------------------
2.0.0 (2016-03-03)
- Remove toJson(..) and fromJson(..) methods from data types.
- Support ProGuard shrinking for Android development and provide example.
- Rename v2 request classes to support future auth styles:
    - DbxFiles -> DbxUserFilesRequests
    - DbxSharing -> DbxUserSharingRequests
    - DbxUsers -> DbxUserUsersRequests
    - DbxTeam -> DbxTeamTeamRequests
- Replace public final references in DbxClientV2 and DbxTeamClientV2 with accessor methods.
- Update longpoll example with better documentation on setting timeout values.

---------------------------------------------
2.0-beta-7 (2016-02-24)
- Updated to latest API specs.

---------------------------------------------
2.0-beta-6 (2016-02-22)
- Updated to latest API specs.
- Use getter methods instead of public final fields.
- Rename exception classes to be consistent with Java practices (e.g. end in "Exception").
- Move DbxException inner classes out into their own files.
- Expose Retry-After backoff for rate limiting exceptions.
- Add configuration setting for automatically retrying failed requests.
- Fix bug that hid certain routes containing union request arguments.
- Add new Java packages for v2 client.
- Break out v2 nested classes into their own files in the appropriate packages.
- Change format of builder methods.
  - Prepend 'with' to method names
- Change format of tagged union classes.
  - getTag() renamed to tag() to avoid naming conflicts
  - Tags without values now referenced as public static final singletons
  - Unions of value-less tags generated as enums
- Add builders for request and response classes.
- Fix deserialization bug with Union containing tags with optional values.
- Make read timeouts more easily configurable for StandardHttpRequestor.
- Add longpoll example.
- Separate integration tests from unit tests and enable unit tests by default.
- Fix android example bugs and linter warnings
  - Fix compilation error
  - Fix upload failure bug
  - Fix download failure bug
  - Update build dependencies
  - Stop using deprecated interfaces

---------------------------------------------
2.0-beta-5 (2016-01-22)
- Updated to latest API specs.
- Change format of tagged union classes.
  - Change getter method format from getAbc() to getAbcValue().
  - Add new isAbc() convenience methods.
  - Add new getTag() method for tag discrimination.
- Accept List instead of ArrayList for requests.
- Fix BadRequest exception for DbxFiles.listFolderLongpoll(String).
- Uppercase enum and static fields.
- Add support for Dropbox API team endpoints.
- Expose localized user messages and request IDs in exceptions.

---------------------------------------------
2.0-beta-4 (2015-12-10)
- Update sharing endpoints to support new paging routes.
- Fix bug that caused sharing calls to fail due to bad shared folder IDs.

---------------------------------------------
2.0-beta-3 (2015-12-01)
- Add a workaround for older Android versions' buggy SecureRandom.
- Fix android example.

---------------------------------------------
2.0-beta-2 (2015-11-13)
- Put "Dbx" prefix on namespace classes (Files -> DbxFiles, etc.)
- Updated to latest API specs.

---------------------------------------------
2.0-beta-1 (2015-10-13)
- Add support for Dropbox API v2.  Moved API v1-specific classes to
  'v1' sub-package.
- Add support for Android.
- Add support for using OkHttp as the HTTP client library.

---------------------------------------------
1.8.2 (2015-10-19)

- Fix bug parsing "photo_info" in file metadata.
- Add support for /account/info fields: email, email_verified,
  name_details.

---------------------------------------------
1.8.1 (2015-09-21)

- Fix bug in version validation code that caused crash at startup.

---------------------------------------------
1.8 (2015-09-14)

- Include SDK version in HTTP requests (via the User-Agent header).
- Fix 'urlState' handling in DbxWebAuth.  Was mistakenly include the
  '|' separator.
- Add support for /delta/latest_cursor and /longpoll_delta.
- Add support for include_media_info=true on /metadata and /delta.
- Add support for using OkHttp as the underlying HTTP client.

---------------------------------------------
1.7.7 (2014-09-02)

- Fix encoding of Unicode characters in API request URL paths.  Bug
  affected systems where Java's "file.encoding" wasn't UTF-8.

---------------------------------------------
1.7.6 (2013-12-09)

- Stricter SSL: Hard-code the ciphersuites and trusted root
  certificates (instead of using the system defaults).
- Add DbxOAuth1Upgrader, which upgrades existing OAuth 1 access tokens
  to OAuth 2 access tokens.
- Add support for /delta's new "path_prefix" parameter.

---------------------------------------------
1.7.5 (2013-09-16)

- Fix crash in getRevisions.

---------------------------------------------
1.7.4 (2013-09-13)

- Fix crash in getAccountInfo, caused by new quota field "datastores".
- Fix file uploading by setting Content-Type explicitly.

---------------------------------------------
1.7.3 (2013-09-05)

- Fix copy/move for folders.
- Fix getMetadataWithChildren for when the file/folder doesn't exist.

---------------------------------------------
1.7.2 (2013-08-22)

- Get thumbnails working (they were completely broken).

---------------------------------------------
1.7.1 (2013-08-21)

- Get chunked uploads working (they were almost completely broken).

---------------------------------------------
1.7 (2013-07-31)

- Added support for most API calls.
- A few minor backwards-incompatibilities.

---------------------------------------------
1.6 (2013-07-07)

- Completely rewritten SDK, focused on web apps (no Android support).
- Many API calls not yet implemented.
- Not backwards compatible with previous versions.
